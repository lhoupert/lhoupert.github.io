---
title: "EOPF Explorer: Sentinel Pipelines for ESA"
date: 2026-07-21
tags: ["earth-observation", "sentinel-1", "zarr", "stac", "argo", "esa"]
summary: "Cloud-native ingestion and Sentinel-1 radiometric terrain correction pipelines that turn Sentinel archives into analysis-ready Zarr, built for ESA's EOPF Explorer."
draft: false
---

## What it is

At Development Seed I work on ESA's EOPF Explorer, building the pipelines that turn raw Sentinel data into analysis-ready, cloud-native datasets. Two pieces have taken up most of my time: ingesting Sentinel products into Zarr, and a production pipeline that applies radiometric terrain correction (RTC) to Sentinel-1 imagery over a mountainous area of interest.

## How it works

The pipelines run on Kubernetes, with [Argo Workflows](https://argoproj.github.io/workflows/) doing the heavy processing and [Argo Events](https://argoproj.github.io/events/) triggering runs as new data lands rather than on a fixed schedule. The terrain correction builds on the Orfeo ToolBox and S1Tiling. Outputs are written as Zarr and catalogued with STAC, so downstream users can search and open exactly the pixels they need without a bulk download step.

I gave a talk at FOSS4G Europe 2026 on the "self-healing" side of this design — how data-driven triggers and good observability let a pipeline recover from the kind of silent failures that scheduled cron jobs tend to hide: [From Cron Job to Self-Healing Pipeline](https://talks.osgeo.org/foss4g-europe-2026/talk/JFCDW9/). A companion repository with a runnable version of the pattern is on GitHub: [lhoupert/argo-stac-eo-pipeline](https://github.com/lhoupert/argo-stac-eo-pipeline).

## Why it matters

Sentinel archives are enormous, and terrain correction is exactly the kind of step that is easy to get subtly wrong and expensive to redo at scale. Getting the data model and the triggering right — so the system only reprocesses what actually changed, and tells you loudly when something breaks — matters as much as the correction maths itself.

*Stack: Kubernetes, Argo Workflows & Events, Zarr, STAC, TiTiler/eoAPI, Orfeo ToolBox / S1Tiling, Python.*
