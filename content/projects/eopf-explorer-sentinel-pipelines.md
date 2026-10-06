---
title: "EOPF Explorer: Sentinel Pipelines for ESA"
date: 2026-07-23
tags: ["earth-observation", "sentinel-1", "sentinel-2", "zarr", "stac", "argo", "esa"]
summary: "Cloud-native Sentinel pipelines for ESA's EOPF Explorer: Sentinel GeoZarr ingestion at scale, self-healing lifecycle automation."
draft: false
---

## What it is

Since November 2025 I've worked on ESA's EOPF Explorer, building the pipelines that turn raw Sentinel data into analysis-ready, cloud-native datasets. My work has mostly been in three areas: converting Sentinel-2 products into GeoZarr at scale, the operational machinery that keeps a large catalogue healthy without manual intervention, and extending the pipeline to Sentinel-1.

## Sentinel-2: GeoZarr ingestion at scale

The backbone of the project was a pipeline that converted Sentinel-2 L2A products into GeoZarr (CF-compliant metadata, multiscale overviews, tuned sharding and compression) and registered each product in a STAC catalogue, so downstream users could search and open exactly the pixels they need without a bulk download step.

## Keeping the catalogue healthy

The pipelines ran on Kubernetes, with [Argo Workflows](https://argoproj.github.io/workflows/) doing the heavy processing and [Argo Events](https://argoproj.github.io/events/) triggering runs as new data landed rather than on a fixed schedule. Around that core sat the lifecycle automation a large catalogue needs: automated storage-tier management to keep recent data fast and older data cheap, expiry-driven retention that cleans up transient products on a schedule, and observability tuned so the system only reprocesses what actually changed.

I gave a talk at FOSS4G Europe 2026 on this "self-healing" design: [From Cron Job to Self-Healing Pipeline](https://talks.osgeo.org/foss4g-europe-2026/talk/JFCDW9/). A companion repository with a runnable version of the pattern is on GitHub: [lhoupert/argo-stac-eo-pipeline](https://github.com/lhoupert/argo-stac-eo-pipeline).

## Sentinel-1: radiometric terrain correction

The newest strand was an RTC pipeline for Sentinel-1 GRD imagery, built as an MVP to show how to produce multidimensional GeoZarr datacubes (time x latitude x longitude) per tile. It was built on the Orfeo ToolBox and S1Tiling, fetched Copernicus DEM tiles on demand, and was triggered by new acquisitions. The MVP covered an area of interest spanning mainland France and the Alps (~160 tiles), appending each acquisition into per-tile datacubes served through TiTiler. I contributed its GeoZarr data model and STAC builders to the open-source [eopf-geozarr](https://github.com/EOPF-Explorer/data-model) library.



*Stack: Kubernetes, Argo Workflows & Events, Zarr, STAC, TiTiler/eoAPI, Python.*
