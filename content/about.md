---
title: "About Me"
date: 2026-10-06
layout: article
---

I'm a cloud engineer at [Development Seed](https://developmentseed.org/), based in Durham, UK. I design and run the pipelines that turn Sentinel and Meteosat archives into analysis-ready, cloud-native datasets, on Kubernetes and Argo Workflows. Before that I was a physical oceanographer for about ten years, and some of how I work today still comes from that time.

## What I work on

Two projects have taken most of my time since I joined in November 2025.

For ESA's [EOPF Sentinel Zarr Explorer](https://dataspace.copernicus.eu/ecosystem/services/eopf-sentinel-zarr-explorer), I worked on the pipelines that convert Sentinel products to GeoZarr and register them in a STAC catalogue, and built most of the lifecycle automation (storage tiers, retention) that a large catalogue needs. I also built a Sentinel-1 radiometric terrain correction MVP that produced per-tile GeoZarr datacubes over France and the Alps, and contributed its data model to the open-source [eopf-geozarr](https://github.com/EOPF-Explorer/data-model) library. There is more on the [project page](/projects/eopf-explorer-sentinel-pipelines/).

For EUMETSAT's Destination Earth Data Lake, I wrote the first architecture decision record and the MVP plan for onboarding the data, then built a large part of the chain that turns satellite products into HEALPix Zarr and Icechunk datacubes, including the MSG SEVIRI, MTG FCI and first Sentinel-3 OLCI cubes. A lot of that job was design rather than code. I turned throughput benchmarks into a capacity plan for the MVP and chose the chunk layout from read benchmarks on the live stores. The data encodings were agreed with EUMETSAT experts before they went into the code, and I wrote the quickstart notebooks that users start from.

Both projects involve several organisations, from the agencies that own the data to the teams who build on it, so a fair share of the design work is agreeing formats and conventions with them before anything gets built.

What I spend the most care on is that the data is correct and stays correct. In practice that means validating STAC metadata before it is published, checking stores against the GeoZarr spec with more than one reader and reporting the gaps upstream, and comparing the catalogue against what should be there, so missing data shows up in a daily report rather than in someone's notebook. I've also learnt to make risky production changes in small, reversible steps: a dry run, then a canary, then the rest. Part of this comes from years of re-running ocean data pipelines by hand 😅 (I wrote about that in [From Cron Job to Self-Healing Pipeline](/posts/04_cron_to_self_healing/)), and the rest I learnt running pipelines in production.

I also try to fix problems upstream rather than work around them. I've contributed GeoZarr dimension selection to [OpenLayers](https://github.com/openlayers/openlayers/pull/17542), a cache fix to [fsspec](https://github.com/fsspec/filesystem_spec/pull/2075), and fixes to tools in the STAC and eoAPI ecosystem. I started a supply-chain security effort at Development Seed, which produced a reusable [security-auditing GitHub Action](https://github.com/developmentseed/action-python-security-auditing) and a long series of small hardening pull requests across open-source geospatial repositories. In 2026 I spoke at FOSS4G Europe and UKEO and helped run an eoAPI + STAC workshop; the FOSS4G details are on the [talks](/talks) page.

## From observations to data people can use

Looking back, the part of the job I keep coming back to is the step between raw observations and the people who use them: the processing code and quality control that end in a documented dataset, ideally with a pipeline that keeps it up to date.

During my PhD I merged 13 hydrographic databases into a quality-controlled set of more than 140,000 temperature profiles, and published the resulting [Mediterranean mixed-layer and heat-storage climatology](https://doi.org/10.17882/46532) as an open dataset.

At SAMS and then NOC, I worked on UK-OSNAP, the UK contribution to [OSNAP](https://www.o-snap.org/), an international array of moorings and gliders across the subpolar North Atlantic. At SAMS I helped plan and run our share of it (the Rockall Trough moorings and the glider missions over the Rockall Plateau), from the mooring cruises to processing and archiving the data. I wrote a MATLAB toolbox to process and quality-control our glider data. I also led the adaptation of the RAPID-MOC mooring processing toolbox for the OSNAP moorings, maintained it, and later extended it to NOC's Iceland Basin moorings; SAMS [still uses it](https://github.com/ScotMarPhys/m_moorproc_toolbox) on its mooring cruises. I published the UK-OSNAP glider datasets at the British Oceanographic Data Centre, and a [2026 study](https://doi.org/10.5194/os-22-167-2026) by the SAMS and NOC team builds on my 2020 paper, which published the first four years of the array's continuous transport measurements, to give a decade-long record.

The two roles in between were different. At OSE Engineering the methods came from operations research rather than oceanography: I packaged vehicle-routing algorithms into Python libraries, with documentation and tutorials, for a delivery-robot prototype. At DWP I co-architected the container platform used to deploy the analytics and AI applications that cyber data scientists and analysts rely on. That is where I learnt to build and secure the infrastructure this kind of work runs on.

At Development Seed the two sides meet again: the pipelines and data models I work on turn satellite archives into datasets that a scientist can open with a few lines of Python.

## Research years

I did an MSc in atmospheric, oceanic and climate sciences at Université Pierre et Marie Curie (now Sorbonne Université) and a PhD in physical oceanography at the Université de Perpignan (2013), on deep convection and the seasonal cycle of the upper ocean in the Mediterranean. After a short postdoc at LOCEAN in Paris, I spent four years at the [Scottish Association for Marine Science](https://www.sams.ac.uk/) in Oban and two at the [National Oceanography Centre](https://noc.ac.uk/) in Southampton, working on the North Atlantic Current in the eastern subpolar gyre with gliders and moorings.

Over those years I published 30+ peer-reviewed papers, four of them as first author, and co-authored more than 50 conference presentations, including 12 invited talks. I took part in 12 research cruises in the North Atlantic and the Mediterranean, about 200 days at sea, including four OSNAP mooring cruises (2015–2018) with international teams, where I also co-planned and co-piloted nine glider missions. That fieldwork is where I learnt most of what I know about planning and coordinating a team under pressure. I also mentored Master's students at sea and on their thesis projects, and reviewed papers for JGR Oceans and Geophysical Research Letters. A short list of papers and open datasets is on my [CV](/cv), and the full list is on [Google Scholar](https://scholar.google.com/citations?user=10K7fIYAAAAJ&hl=en).

Outside work I run a small homelab and explore the UK and Europe in a campervan with my family 🚐.
