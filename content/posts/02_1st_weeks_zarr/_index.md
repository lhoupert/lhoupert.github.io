---
title: "When Zarr Stopped Being a File Format: Notes from my first Weeks at Development Seed!"
date: 2025-11-25
draft: true
layout: article     
tags: ["zarr", "cloud-native", "data-formats", "earth-observation", "learning", "technical"]
summary: "My first weeks learning Zarr revealed it's not just NetCDF for the cloud. It's an API that maps array operations onto key-value storage, fundamentally changing how we design data pipelines for Earth observation."
---


![Ocean observing systems including moored buoys and profiling floats](ocean-observing-network.jpg "Ocean observing systems including moored buoys and profiling floats. Source: Figure 1, [Frontiers in Marine Science](https://www.frontiersin.org/journals/marine-science/articles/10.3389/fmars.2020.00697/full)")

For a big part of my career, I built data processing systems for oceanographic observations. I designed pipelines that ingested data from underwater buoys, research vessels, and satellite instruments. When you work with observational data at scale, you develop strong opinions about data formats. [NetCDF](https://www.ogc.org/standards/netcdf/) became my default: robust, well-documented, handles multi-dimensional scientific arrays with complete metadata.

So when I transitioned to cloud engineering and [started working with Earth observation data infrastructure](https://lhoupert.fr/posts/01_joining_development_seed/), I made what seemed like a reasonable assumption: Zarr would be NetCDF for the cloud. Same conceptual model, just optimized for object storage instead of POSIX filesystems.

That assumption lasted about a week 😅
## What Actually Happened

I started my Zarr learning with Lindsey Nield's excellent explainer ["What is Zarr?"](https://earthmover.io/blog/what-is-zarr/) on the Earthmover blog. It's a solid introduction, clearly written, hits all the key points. But something kept not clicking for me. The article compared Zarr to other file formats, talked about chunks and compression, showed storage layouts. It all made sense on paper, but I couldn't quite grasp why everyone was so excited about it.

Then I read Davis Bennett's presentation from the resources published in the [2025 Zarr Summit recap](https://cloudnativegeo.org/blog/2025/11/2025-zarr-summit-recap/). In his talk ["What is Zarr (and what isn't it)"](https://docs.google.com/presentation/d/1QB-EKo1qFqIreqehowBmz5kFJsUQCgYxprgrVabF35Y/edit?usp=sharing), Bennett explains something that reframed completely how I understood Zarr: **Zarr is an API or protocol, not a conventional file format**. For my scientist friends who are struggling in grasping the meaning of an API, it can be summarized by [a set of rules and definitions that let software systems communicate with each other](https://github.com/resources/articles/what-is-an-api#apis-at-github). 

I'd been approaching Zarr like it was a container format with some clever cloud optimizations. But I have been missing the point... Zarr defines how to map "array semantics" onto [key-value storage systems](https://en.wikipedia.org/wiki/Key%E2%80%93value_database). It doesn't care where or how the underlying data is physically stored, those keys can point to files on disk, objects in [cloud object storage](https://cloud.google.com/learn/what-is-object-storage), or entries in a database. 

This is an important distinction compare to traditional file format as it completely made me changes the way I think on how to design data pipelines.


## A Sensor Network Analogy

In my oceanographic work, we operated networks of underwater instruments. Autonomous gliders, moored buoys, profiling floats, each collecting continuous measurements. When analysing large amount of data, I learned quickly that "download everything first, then analyze" doesn't scale well. At that time I wished there was an efficient way to support selective queries (give me temperature profiles between these dates at these depths), lazy evaluation (don't fetch data you won't use), distributed access (multiple researchers querying different aspects simultaneously), and partial reads (get monthly averages at a specific location without downloading daily sample of an entire region).

Zarr's key-value architecture enables exactly these patterns for array data. 


![Zarr hierarchical structure showing groups and arrays](zarr-hierarchy-diagram.png "Zarr hierarchical structure showing groups and arrays. Source: [Zarr Documentation](https://zarr-specs.readthedocs.io/en/latest/)")

## Different Ways to Access Data

Working through the [EOPF tutorial on Zarr](https://eopf-toolkit.github.io/eopf-101/22_zarr_structure_S1GRD.html) (Earth Observation Processing Framework) changed how I was thinking about the problem. The tutorial shows different ways to access the same Sentinel-1 radar data stored in Zarr format. At first this felt like API complexity. Then I realized each pattern represents a different mental model, and both are equally valid depending on your workflow.

Here's the first approach, opening the entire hierarchical structure:

```python
import xarray as xr

# Open the complete data tree
dt = xr.open_datatree(url, engine='zarr', chunks={})
```

This gives you the full organizational structure. Groups, subgroups, the whole hierarchy. It's exploratory. You're getting oriented in unfamiliar data. In NetCDF terms, this would be like opening a file and running `ncdump -h` to see what variables exist and how they're organized.

The second approach jumps directly to a specific group. You can do it in two different ways:

```python
# Access a specific measurement group directly
ds = xr.open_dataset(
    url, 
    engine='zarr', 
    group='measurements/VV',
    chunks={}
)
```

or

```python
# Navigate to a group, then convert to a dataset
ds = dt["measurements/VV"].to_dataset()
```

You already know what you want. You know the data structure. Just get that specific variable without loading anything else. This is the "I've worked with this dataset before" pattern. In my OSNAP mooring array processing, this would be equivalent to querying just the current meter data from a specific mooring location without pulling temperature and salinity measurements from all the other moorings across the North Atlantic.

Something crucial about how both of these are accessing data: there is no download step, it is over HTTP from a remote URL. No local caching is needed before you start working. The data lives where it lives, and you're describing your access pattern. Zarr figures out which chunks to fetch based on what you're actually requesting.

The `chunks={}` parameter preserves the original chunking from the metadata. The idea behing it is to respect the intent of whoever organized the data. They chose those chunk dimensions for a reason, probably based on common access patterns, and using `chunks={}` means "trust those decisions".



![Schematic of the OSNAP mooring array](osnap_array_schematic.jpg "Schematic of the OSNAP mooring array. Source: [OSNAP website](https://www.o-snap.org/wp-content/uploads/2013/12/osnap_array_schematic_20160401-1024x534.jpg.webp)")

## Chunks as Architecture, Not Optimization

In NetCDF, chunks are a performance tuning option. You can use them to optimize read patterns, or you can ignore them entirely. The format still works.

In Zarr, chunks define the data structure itself. Bennett's [other presentation](https://docs.google.com/presentation/d/1mFJrOplbbnzAcjXR_n5l4kT-nEgI8c2v-iwtxIL51QY/edit?slide=id.p) makes this clear: Zarr stores large arrays as separate sub-arrays. Each chunk is an independent unit that can be read, written, or compressed separately. The format is lazy. It only creates data chunks when values are written.

This maps perfectly to distributed scientific workflows. When I was processing data from the OSNAP mooring array, we didn't collect uniform spatial grids across the North Atlantic. We had moorings at specific locations spanning from Labrador to Scotland, each equipped with multiple instruments at different depths measuring temperature, salinity, and velocity. Each mooring was its own data unit, each sensor type its own stream. The observational data was inherently chunked by location, by instrument, by depth. 

Zarr formalizes this approach. Chunks themselves become the fundamental units and the chunking strategy can become an expression of your data's structure and your access patterns.

## What This Changes

The remote access pattern from the EOPF tutorials reflects how Zarr fundamentally works. You point to a URL, describe what you want, and the system fetches the relevant chunks. There is no need to download the data before running a processing workflow, or manage local copies of the data. 

For Earth observation workflows, this matters. Satellite data archives are massive. A single Sentinel-1 scene can be gigabytes. An analysis might only need a specific polarization, a particular time range, a subset of the spatial extent. With traditional file formats, you still need to download the whole file to read parts of it. With Zarr's key-value model, you fetch only the chunks that matter for your specific query.

I think that is why everyone building cloud-native geospatial infrastructure is converging on Zarr. It's not only because it's more efficient than alternatives, it's because it models data access patterns that match how we actually work with Earth observation data.


![Copernicus Sentinel-1 satellite](sentinel-1-satellite.jpg "Copernicus Sentinel-1 satellite. Source: [Copernicus](https://www.copernicus.eu/en/news/news/observer-celebrating-decade-copernicus-sentinel-1)")

## What I'm Still Learning

I'm in my 2nd week into understanding Zarr, and there's plenty I still don't fully grasp: the differences between Zarr V2 and V3, differences between Zarr and GeoZarr, differences between Zarr conventions and Zarr extension and how they relate to the core specification, or details of chunk encoding and compression options. But the fundamental mental model shift has happened: stop thinking about files, start thinking about array protocols over key-value stores.

If you're coming from NetCDF or HDF5, this requires unlearning some assumptions. File handles, sequential reads, monolithic containers. These concepts don't map cleanly to Zarr because I think Zarr isn't trying to be a better file format but it operates on different principles.

For scientists and data engineers building systems to handle large-scale Earth observation data, that difference matters. There is a learning curve, but I think it is worth, as it is certainly [the future for scientific data](https://earthmover.io/blog/building-the-future-of-scientific-data-at-the-zarr-summit/). 

