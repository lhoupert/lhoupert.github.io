---
title: "Open Source"
date: 2026-11-16
tags: ["open-source", "geospatial", "security", "stac", "zarr"]
summary: "Companion code, security tooling, and upstream contributions across the cloud-native geospatial stack."
draft: false
---

## Companion code

- [lhoupert/argo-stac-eo-pipeline](https://github.com/lhoupert/argo-stac-eo-pipeline) — a runnable version of the self-healing Argo + STAC ingestion pattern from my FOSS4G Europe 2026 talk.
- [lhoupert/qgis-eopf-geozarr](https://github.com/lhoupert/qgis-eopf-geozarr) — getting started with EOPF Explorer GeoZarr (Sentinel-2 L2A, Zarr v3 multiscales) in QGIS.

## Security tooling

Security and supply-chain hardening is a recurring thread in my work. One piece I can point to publicly is [action-python-security-auditing](https://github.com/developmentseed/action-python-security-auditing), a reusable GitHub Action for auditing Python projects; it now fails, rather than passing, when pip-audit cannot run.

## Upstream contributions

I try to push fixes and features back to the tools I rely on rather than working around them:

- [Non-spatial dimension selection for the GeoZarr source](https://github.com/openlayers/openlayers/pull/17542) — OpenLayers (merged)
- [Atomic whole-file cache writes](https://github.com/fsspec/filesystem_spec/pull/2075) — fsspec (merged), fixing a long-latent caching race
- titiler-openeo: [a fix for STAC items with a null datetime](https://github.com/sentinel-hub/titiler-openeo/pull/473), [a minimal Wolfi-based image](https://github.com/sentinel-hub/titiler-openeo/pull/476) [scanned in CI and rebuilt nightly](https://github.com/sentinel-hub/titiler-openeo/pull/478), and [the database schema created by a Helm job instead of at import](https://github.com/sentinel-hub/titiler-openeo/pull/479) (all merged)
- STAC and eoAPI tooling: [releases on merge with release-please](https://github.com/stac-utils/titiler-pgstac/pull/350) in several eoAPI repositories, such as titiler-pgstac, and smaller container images, for example [STAC Manager, from 3.75 GB to 55 MB](https://github.com/developmentseed/stac-manager/pull/108) (merged)
- [SHA-pinning GitHub Actions](https://github.com/stac-utils/stac-fastapi/pull/897) — stac-fastapi (merged), and [the same hardening](https://github.com/PyCQA/bandit-action/pull/29) proposed for bandit-action
- [A GDAL bug report](https://github.com/OSGeo/gdal/issues/15380) with a minimal reproduction: in GDAL 3.13, a zoomed-out read of a Zarr array with overviews first reads the full-resolution data before using the overview

Most of my day-to-day output lands as merged pull requests across a handful of open-source organizations in the geospatial and cloud-native space.
