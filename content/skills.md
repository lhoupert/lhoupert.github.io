---
title: "Skills"
date: 2025-11-12
lastmod: 2026-10-09
description: "The tools and practices I reach for day to day: cloud-native geospatial data, how I deliver, Kubernetes platforms, working with teams, and Python."
showDate: false
showDateUpdated: true
showReadingTime: false
showAuthor: false
showPagination: false
---

<!--
Page shape (keep it at each refresh):
- Sections in order of importance: geospatial, how I work, infrastructure, teams, Python, evolution.
- Each H2 = one voice paragraph, then one label/value list, then at most one aside.
- A tool lives in exactly one row. Glance items must also appear in a row of the linked section.
- Lists are definition lists: a label line, then ": value". Leave a BLANK LINE between entries,
  and put {.stack} on the line right after the last entry.
- Never put a heading inside a details block (the TOC link would not open it).
- Bump lastmod at each refresh.
-->

This is a snapshot of the tools and practices I actually reach for day to day: the Earth observation data I work with and how I go about it, the infrastructure I run things on, how I work with teams, and the language I write it all in. Most of it grew out of one recurring problem: making large-scale scientific data less painful to work with. If you want the story of how I got from ocean data to Earth observation, that is on the [about page](/about).

[Data & geospatial](#geospatial)
: STAC · Zarr / GeoZarr · Icechunk · TiTiler & eoAPI

[How I work](#how-i-work) & [teams](#leadership)
: ADRs before code · dry runs and canaries · in-depth reviews · runbooks · workshops

[Infrastructure](#infrastructure)
: Kubernetes · Argo Workflows & Events · Flux & Helm · Terraform · GitHub Actions

[Python](#python)
: uv · ruff · pyright · pytest · FastAPI · Xarray
{.stack .glance}

## 🗺️ Geospatial data engineering {#geospatial}

In oceanography I processed data from gliders, moorings, research ships and satellite altimetry, and published some of the results as open datasets. The problems carry over to Earth observation almost unchanged. You still need quality control and metadata that a stranger can understand, only now the data lives in object storage and the formats have to let people read just the part they need.

Formats & catalogues
: STAC · Zarr v3 · GeoZarr · Icechunk · HEALPix · NetCDF

Services
: TiTiler · eoAPI
{.stack}

**Ocean data then, Earth observation now**

Formats
: **Ocean:** NetCDF, HDF5\
  **Earth observation:** STAC, Zarr, cloud-optimized geospatial formats

Processing
: **Ocean:** time-series and spectral analysis, gridding, quality control, uncertainty quantification\
  **Earth observation:** data pipelines

Scale
: **Ocean:** ocean model output and reanalyses, plus 140,000+ quality-controlled profiles merged from 13 databases\
  **Earth observation:** terabyte-scale satellite archives

Metadata
: **Ocean:** CF conventions, standardized vocabularies, documented datasets with DOIs\
  **Earth observation:** STAC catalogs, data-model version recorded in each item

Quality
: **Ocean:** calibration of moored CTD sensors against ship casts, sensor intercalibration, automatic and manual QC\
  **Earth observation:** STAC validation before publishing, GeoZarr conformance checks across readers (GDAL, TiTiler, OpenLayers)
{.stack}

## 🧭 How I work {#how-i-work}

A good part of my job doesn't show on the commit graph: working out what to build before building it, and how to change a system people already depend on without breaking it.

Architecture decisions
: Architecture decision records and MVP breakdowns written before the code, with open questions left explicit for the team

Capacity & data layout
: Capacity plans from measured throughput; chunk and shard layouts chosen from read benchmarks on the live data

Standards
: STAC, Zarr/GeoZarr and CF conventions

Releases & versioning
: Automated semantic releases and pinned versions; the data-model version recorded in the catalogue; each data release tied to a tagged snapshot

Production changes
: Dry runs and canaries before full production runs, run limits enforced inside the tool, and an undo path rehearsed before the big runs

Working with coding agents
: Coding agents for exploring code, investigating and reviewing; changes are not shipped until I can explain them; adversarial agents to challenge and test architecture design and decisions
{.stack}

## 🏗️ Infrastructure & DevOps {#infrastructure}

I discovered DevOps practices out of necessity: managing research data across multiple environments taught me that manual processes don't scale, and inconsistency often leads to problems. Now I find myself gravitating toward automation not just for efficiency and repeatability but because it forces clarity in thinking. _"If you can't automate it, you probably don't understand it well enough yet."_

Orchestration
: Kubernetes (OVH/OpenStack) · Argo Workflows (batch pipelines) · Argo Events (data-driven triggers) → data-driven Earth observation pipelines

CI/CD
: GitHub Actions · Conventional Commits (GitLab CI previously) → automated, reproducible releases

GitOps & IaC
: Flux (GitOps reconciliation) · Helm (packaging) · Terraform (multi-environment) → declarative multi-environment deployments

Containers
: Docker · multi-stage builds · Chainguard · minimal base images

Security
: Prowler · Trivy · zizmor · SHA-pinned actions · Dependabot · Keycloak/OIDC → supply-chain and platform hardening

Observability
: Grafana · Loki · Prometheus · Falco → catching silent failures early

AWS
: boto3 · AWS CDK constructs · Lambda functions
{.stack}

My experience with cloud infrastructure has taught me to appreciate both the technical challenges of system design and the practical impact these systems have on development teams. Container security emerged as a natural extension of my infrastructure work when I began focusing on platform reliability and team productivity. Working with minimal base images has shown me that security practices can actually simplify operations: fewer vulnerabilities mean less time spent on patches and more predictable deployment cycles.

## 👥 Team leadership & enablement {#leadership}

> The greatest good you can do for another is not just share your riches, but reveal to them their own.
>
> <footer>— Benjamin Disraeli</footer>


**Now, at Development Seed**
- Reviewing colleagues' and partners' pull requests in depth before release
- Writing runbooks and playbooks the team can reuse, for example on container hardening and on registering datacube releases
- Helping run [eoAPI + STAC workshops]({{< relref "talks" >}}), including prototyping isolated per-participant eoAPI stacks on Kubernetes for FOSS4G:UK 2026

{{< details summary="**Earlier, at DWP (2022–2025)**: mentored four junior engineers · onboarding guides · test coverage from 10% to 85%" class="skill-more" >}}
- Mentored four junior engineers through pair programming and knowledge sharing
- Regular debugging sessions that became teaching moments
- Wrote onboarding guides for new team members
- Created reusable Terraform modules and Docker templates encoding best practices
- Raised test coverage from 10% to 85% on two production web apps
- Implemented pre-commit hooks and CI/CD standards balancing guidance with flexibility
{{< /details >}}

{{< details summary="**Earlier, in research (2010–2021)**: trained PhD students · OSNAP cruises with teams of 10+ · peer review for JGR Oceans and GRL" class="skill-more" >}}
- Helped train PhD students and research staff in computational methods
- Helped plan and run OSNAP mooring cruises with international teams of 10+ people
- Mentored Master's students on research cruises and their thesis projects
- Contributed to the OceanGliders water-transformation task team
- Reviewed papers for JGR Oceans and Geophysical Research Letters, and research proposals
{{< /details >}}

**Learning Through Collaboration**: Some of my most valuable moments happen when working alongside my teammates on challenging problems. Those debugging sessions often become mutual learning experiences where we both discover better approaches to error handling and system design.

**Freedom Through Structure**: I've found it interesting how clear technical guidelines can actually increase creativity. When the team doesn't have to worry about formatting or basic quality checks, I think it creates more mental space to focus on solving the actual problems at hand.

**From Solving to Enabling**: I shifted my way of thinking from "I know how to fix this" to "How can we build systems so this problem becomes easier for everyone to solve?"

## 🐍 Python {#python}

I transitioned to Python as my primary language in 2020 after extensive work with MATLAB in research. What began as exploratory data analysis for oceanographic datasets has evolved into building production Flask applications, maintaining reusable Python packages and implementing comprehensive testing frameworks. I've found that each domain I worked in taught me something different about writing maintainable, reliable code.

Tooling
: uv · ruff · pyright · pre-commit hooks

Analysis
: NumPy · Pandas · Xarray

Testing
: pytest · integration testing · mocking strategies

Web frameworks
: Flask · Django · FastAPI

Visualization
: Matplotlib · Plotly · Cartopy (geospatial) · Folium

ML & statistics
: scikit-learn · statistical modeling · Monte Carlo methods

Documentation
: Sphinx · MkDocs · automated API docs
{.stack}

## 🎯 My technical evolution {#evolution}

The diagram below shows how I understand my professional development, with **Problem Solving** as "the driving force".

The three branches reflect my career evolution: **Scientific Thinking** from research years where you learn to be systematic and question everything, **Engineering Practices** developed transitioning to software development, and **Team Leadership** emerging as I found sharing knowledge often more impactful than individual work. These areas reinforce each other: my research background helps me approach infrastructure methodically, engineering experience makes me a better mentor, and team work drives more systematic thinking.

The **Continuous Learning** foundation feels essential: every role change, technology, or colleague conversation adds to this framework. It's how I approach growth: staying curious, building on what I know, and helping others grow too.

<div class="evo">
  <p class="evo-band">Problem solving</p>
  <div class="evo-cols">
    <div class="evo-card"><p class="evo-title">Scientific thinking</p><p>systematic · rigorous · data-driven</p></div>
    <div class="evo-card"><p class="evo-title">Engineering practices</p><p>automation · security · scalability</p></div>
    <div class="evo-card"><p class="evo-title">Team leadership</p><p>mentoring · pairing · standards</p></div>
  </div>
  <p class="evo-band">Continuous learning</p>
</div>

**What I'm currently focussing on**
- **Knowledge Sharing**: Contributing to documentation and learning resources for geospatial data engineering
- **Open Source Participation**: Engaging with communities building Earth observation infrastructure
- **Science to Software**: Turning scientific data and methods into tools and datasets other people use, from glider and mooring toolboxes in my oceanography years to analysis-ready satellite datacubes today
