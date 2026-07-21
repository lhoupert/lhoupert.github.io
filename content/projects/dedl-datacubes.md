---
title: "Destination Earth Datacubes for EUMETSAT"
date: 2026-07-21
tags: ["earth-observation", "zarr", "healpix", "icechunk", "eumetsat", "datacubes"]
summary: "Turning MSG, MTG and Sentinel-3 archives into analysis-ready HEALPix Zarr datacubes for EUMETSAT's Destination Earth Data Lake."
draft: false
---

## What it is

For [EUMETSAT's](https://www.eumetsat.int/) Destination Earth Data Lake (DEDL) — part of the EU's [Destination Earth](https://destination-earth.eu/) initiative — I build pipelines that turn geostationary and polar-orbiting satellite archives into analysis-ready datacubes. The inputs are instruments like MSG SEVIRI, MTG FCI and Sentinel-3 OLCI; the outputs are HEALPix-gridded [Zarr](https://zarr.dev/) cubes with versioned, transactional storage through [Icechunk](https://icechunk.io/).

## How it works

HEALPix gives an equal-area grid over the sphere, which is a much more natural fit for whole-Earth data than a plate-carrée raster. Storing the cubes as Zarr with Icechunk means downstream users get consistent snapshots and can append new time steps without rewriting history. A lot of the engineering effort goes into the access pattern: shaping the data so that a common query touches as few stored objects as possible, because on object storage the number of requests often matters more than the number of bytes.

## Why it matters

Destination Earth is building digital twins of the planet, and those twins are only as useful as how quickly a researcher can pull the slice of data they actually need. Getting the grid and the storage layout right is what turns a multi-terabyte archive into something you can explore interactively.

*Stack: HEALPix, Zarr, Icechunk, Xarray, Kubernetes, Argo Workflows, Python.*
