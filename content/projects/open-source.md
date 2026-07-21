---
title: "Open Source"
date: 2026-07-21
tags: ["open-source", "geospatial", "security", "stac", "zarr"]
summary: "Companion code, security tooling, and upstream contributions across the cloud-native geospatial stack."
draft: true
---

## Companion code

- [lhoupert/argo-stac-eo-pipeline](https://github.com/lhoupert/argo-stac-eo-pipeline) — a runnable version of the self-healing Argo + STAC ingestion pattern from my FOSS4G 2026 talk.

## Security tooling

Security and supply-chain hardening is a recurring thread in my work. One piece I can point to publicly is [action-python-security-auditing](https://github.com/developmentseed/action-python-security-auditing), a reusable GitHub Action for auditing Python projects.

## Upstream contributions

I try to push fixes and features back to the tools I rely on rather than working around them:

- [Non-spatial dimension selection for the GeoZarr source](https://github.com/openlayers/openlayers/pull/17542) — OpenLayers (merged)
- [Atomic whole-file cache writes](https://github.com/fsspec/filesystem_spec/pull/2075) — fsspec (open), fixing a long-latent caching race
- [SHA-pinning GitHub Actions](https://github.com/stac-utils/stac-fastapi/pull/897) — stac-fastapi (merged), and [the same hardening](https://github.com/PyCQA/bandit-action/pull/29) proposed for bandit-action (open)

Most of my day-to-day output lands as merged pull requests across a handful of open-source organizations in the geospatial and cloud-native space.
