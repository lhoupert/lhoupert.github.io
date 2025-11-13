---
title: "Joining Development Seed to Build Earth Observation Infrastructure"
date: 2025-11-13
draft: false
layout: article     
tags: ["career", "development-seed", "earth-observation", "geospatial", "announcement"]
summary: "Excited to announce I'm joining Development Seed as a Cloud Engineer to work on geospatial infrastructure for ESA and ECMWF. From oceanographic fieldwork to satellite data engineering, my journey with Earth observations continues!"
---


![Development Seed Logo](DevelopmentSeedLogo.png)

I am excited to announce that I will be joining [Development Seed](https://developmentseed.org/) next week as a Cloud Engineer, working on cloud-native geospatial pipelines and AI-driven data tools for partners such as the [European Space Agency (ESA)](https://www.esa.int/) and the [European Center for Medium-Range Weather Forecasts (ECMWF)](https://www.ecmwf.int)! On top of that, I am very thrilled about Development Seed's approach to building open-source solutions by default!


## From Ocean Observations to Cloud Engineering

My path into Earth observation data has been a bit unusual. I started by collecting oceanographic measurements at sea; I spent more than 200 days on research vessels where we used various instruments to measure ocean physical parameters such as temperature, salinity, and velocity. I also used a lot of underwater gliders: autonomous, propeller-less robots that use changes in buoyancy and wings to move through the water column and collect oceanographic data. Their multi-month operational autonomy allows coverage of remote areas, supports long-term monitoring, and allows for consistent measurements across vast distances.

My observationalist work involved integrating these observations with other sources of climate data such as satellite observations and ocean models, developing quality control workflows for these multi-platform observations, implementing statistical and physics-based analysis methods for spatial variability studies, and publishing my results in scientific articles.

![Schematic of the most common type of measurement techniques used by oceanographers to observe the oceans](Ocean_Observation_Techniques.png "Schematic of the most common type of measurement techniques used by oceanographers to observe the oceans. Source:  [Marine Copernicus](https://marine.copernicus.eu/explainers/operational-oceanography/monitoring-forecasting/in-situ)")


In 2021, after more than a decade in academic research, I decided to leave my research career to take a research engineer position at OSE Engineering, a fully remote role. One of the main reasons why I decided to quit academia is that I became increasingly curious about the engineering challenges behind the data systems I used regularly. As a researcher, I relied on these systems for oceanographic analysis, but I wanted to understand how they actually work from the inside: how data services handle performance issues, how infrastructure is managed when systems fail. When processing pipelines encountered problems or performed poorly, I wanted to understand why and learn how to fix them rather than just reporting issues.

This shift required learning backend development, system architecture, and software engineering best practices. Over the past 4 years, I have built Python-based backend systems and co-managed AWS infrastructure using Terraform. The technical stack I used evolved significantly since my researcher days! I went from MATLAB scientific computing to production-grade Python services and from research-focused workflows to scalable cloud architectures. My expertise also broadened significantly, evolving from single-domain expertise to cross-functional engineering approaches.

## Coming Full Circle

Now I am back in the field of Earth observation! This time I will be working with satellite data and geospatial services from an engineering and product perspective, rather than a user perspective. At Development Seed, I will be combining scientific domain knowledge with cloud infrastructure expertise to make Earth observation data more accessible through modern engineering practices. I will work with partners such as the [European Space Agency](https://www.esa.int/) and the [European Center for Medium-Range Weather Forecasts](https://www.ecmwf.int). My background in Earth system physics, environmental data collection, and cloud-native engineering all come together in this role! I think I'll be well-prepared for the technical challenges ahead.

![Range of ESA satellites used for Earth observation missions](ESA-Earth_observation_missions.jpeg "Range of ESA satellites used for Earth observation missions. Source: [ESA](https://www.esa.int/ESA_Multimedia/Images/2019/05/ESA-developed_Earth_observation_missions)")

## Why Development Seed and These Projects

While I was going through the interview process, I discovered the vast range of Development Seed projects and I was very impressed by both their diversity and their depth! It really matches the kind of projects I would like to contribute to. Here are some examples of such projects:

### Global Nature Watch

**[Global Nature Watch](https://developmentseed.org/blog/2025-10-16-global-nature-watch/)** is "_an open, AI-powered system that transforms groundbreaking land monitoring data into intelligence to understand Earth's landscapes_". The platform combines 80+ peer-reviewed datasets into a conversational AI interface that makes environmental intelligence accessible across 170 languages. The technical approach uses AI for orchestration rather than content generation which ensures reliable, reproducible outputs grounded in peer-reviewed science. Indigenous communities in the Philippines are using this technology to defend ancestral territories, and Brazilian cooperatives are designing finance products for smallholder farmers. This is exactly the type of real-world impact that motivates me when building software products!

### Zarr Ecosystem Development

**Zarr ecosystem development** shows Development Seed's commitment to advancing core infrastructure. The work on [VirtualiZarr and Zarr v3](https://developmentseed.org/blog/2025-10-13-zarr/) directly addresses challenges I faced in oceanography when trying to work with massive climate datasets efficiently. The collaboration with ESA to adopt Zarr for Sentinel missions means analysts can stream only the data they need instead of downloading large zip files.

### Obstore

**[Obstore](https://developmentseed.org/blog/2025-08-01-obstore/)** shows the kind of engineering fundamentals that excite me! The goal is to build a stateless, Rust-backed Python library for object storage access. It might seem like infrastructure work, but it directly impacts python performance when working in cloud-native solution as it enables everything else to run faster and more reliably. The focus on speed, and clarity/interoperability corresponds to the kind of engineering quality I value.

### Cloud-Native Data Transformation

**Cloud-native data transformation projects** like the [Spatial Access Lab work](https://developmentseed.org/blog/2025-10-08-spatial-access-lab/) demonstrate how modern tools can make public data truly accessible. The project converts Canada's Spatial Access Measures from legacy CSVs to GeoParquet, then builds an entirely browser-based analytical interface using DuckDB-WASM and deck.gl.

### eoAPI

**[eoAPI](https://github.com/developmentseed/eoAPI)** brings together several state-of-the-art projects to create a complete Earth Observation API framework! The integration of pgSTAC, STAC API, TiTiler, and other components shows the power of combining existing open-source tools into coherent systems. This modular, standards-based approach really matches the way I think about building sustainable infrastructure.

All these projects share common threads: they make scientific data more accessible and they build on open standards and open-source tools. In addition, they contribute to environmental monitoring, climate action, and open science. But these projects also face substantial (and interesting!) technical challenges such as working with planetary-scale datasets, building AI systems that remain grounded in scientific rigor, or creating infrastructure that runs efficiently across multiple cloud providers. This combination of technical depth and real-world impact is exactly what attracted me to Development Seed!

![True color image of the Earth from space](Earth_from_Space.jpg "True color image of the Earth from space. This image is a composite image collected over 16 days by the [MODIS](https://en.wikipedia.org/wiki/MODIS) sensor on NASA’s [Terra](https://en.wikipedia.org/wiki/Terra_\(satellite\)) satellite. Source: [NASA/GSFC/Reto Stöckli, Nazmi El Saleous, and Marit Jentoft-Nilsen](http://earthobservatory.nasa.gov/IOTD/view.php?id=885)")

## Looking Ahead

I think I'm starting from a solid technical foundation: I have experience in Python backend development, cloud-native infrastructure with AWS and Terraform, and with scientific computing libraries like Xarray for multi-dimensional data analysis. That said, there are several technology areas I'll need to learn:

- **The geospatial data ecosystem** (STAC, Zarr, Cloud-Optimized GeoTIFFs, and libraries like GDAL and rio-tiler) represents new formats and standards for making Earth observation data accessible at scale.
- **Kubernetes** in production environments will require moving beyond my ECS experience.
- **Modern AI-driven tools for building natural language interfaces to scientific data** represent a different approach from the traditional machine learning models I have deployed previously.

Now that I am working for an organisation that is _open by default_, I have no excuse not to document my learning journey 😄. I'll do this through regular blog posts. I plan to focus them on technical discoveries and challenges encountered. Beyond documenting my own learning, I hope these posts will help others exploring the intersection of scientific computing, geospatial technologies, and modern cloud infrastructure.
