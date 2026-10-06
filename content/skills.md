---
title: "My Technical Evolution"
date: 2025-11-12
layout: page
---

This is a snapshot of the tools and practices I actually reach for day to day, grouped by layer: the language I write in, the data and geospatial stack I work with, the infrastructure I run things on, and how I work with teams. Most of it grew out of one recurring problem: making large-scale scientific data less painful to work with. If you want the story of how I got from ocean data to Earth observation, that is on the [about page](/about).

## 🐍 Python Development Experience

I transitioned to Python as my primary language in 2020 after extensive work with MATLAB in research. What began as exploratory data analysis for oceanographic datasets has evolved into building production Flask applications, maintaining reusable Python packages and implementing comprehensive testing frameworks. I've found that each domain I worked in taught me something different about writing maintainable, reliable code.

### Core Development
- **Language Experience**: Python since 2020, procedural, OOP
- **Modern Tooling**: `uv`, `ruff`, `pytest`, `pyright`, pre-commit hooks
- **Web Frameworks**: Flask, Django, FastAPI

### Data & Scientific Computing
- **Geospatial Stack**: Rasterio, GDAL, PyProj, GeoPandas, Shapely, S1Tiling/OTB
- **Data Formats**: STAC & pgSTAC, Zarr v3, GeoZarr, Icechunk, VirtualiZarr, Cloud-Optimized GeoTIFFs (COGs), NetCDF, HDF5, HEALPix
- **Cloud-native tooling**: TiTiler, eoAPI
- **Analysis Stack**: NumPy, Pandas, Xarray
- **Visualization**: Matplotlib, Plotly, Cartopy (geospatial), Folium
- **ML/Stats**: scikit-learn, statistical modeling, Monte Carlo methods

### Infrastructure Integration
- **Cloud SDKs**: boto3, AWS CDK constructs, Lambda functions
- **Documentation**: Sphinx, MkDocs, automated API docs
- **Testing**: pytest, integration testing, mocking strategies

<br>

## 🗺️ Geospatial Data Engineering

In oceanography I processed data from gliders, moorings, research ships and satellite altimetry, and published some of the results as open datasets. The problems carry over to Earth observation almost unchanged. You still need quality control and metadata that a stranger can understand, only now the data lives in object storage and the formats have to let people read just the part they need.

| Domain | Experience & Approaches | Current Applications |
|--------|------------------------|---------------------|
| **Data Formats** | NetCDF, HDF5 → STAC, Zarr, COGs | Cloud-optimized geospatial formats |
| **Processing** | Time-series and spectral analysis, gridding, quality control, uncertainty quantification | Earth observation data pipelines |
| **Scale** | 140,000+ quality-controlled profiles merged from 13 databases, multi-platform integration | Terabyte-scale satellite archives |
| **Metadata** | CF conventions, standardized vocabularies, documented datasets with DOIs | STAC catalogs, data-model version recorded in each item |
| **Quality** | Calibration of moored CTD sensors against ship casts, sensor intercalibration, automatic and manual QC | STAC validation before publishing, GeoZarr conformance checks across readers |

<br>

## 🔄 DevOps & Automation Experience

I discovered DevOps practices out of necessity - managing research data across multiple environments taught me that manual processes don't scale, and inconsistency often leads to problems. Now I find myself gravitating toward automation not just for efficiency and repeatability but because it forces clarity in thinking. _"If you can't automate it, you probably don't understand it well enough yet."_


| Domain | Tools & Approaches | Current Focus |
|--------|-------------------|--------------|
| **Orchestration** | Kubernetes (OVH/OpenStack), Argo Workflows & Events | Data-driven Earth observation pipelines |
| **CI/CD** | GitHub Actions, Conventional Commits (GitLab CI previously) | Automated, reproducible releases |
| **GitOps & IaC** | Flux, Helm, Terraform | Declarative multi-environment deployments |
| **Security** | Prowler, Trivy, zizmor, SHA-pinned actions, Dependabot, Keycloak/OIDC | Supply-chain and platform hardening |
| **Observability** | Grafana, Loki, Prometheus, Falco | Catching silent failures early |

<br>

### 🏗️ Infrastructure & Platform Layer

My experience with cloud infrastructure has taught me to appreciate both the technical challenges of system design and the practical impact these systems have on development teams. Each component serves a specific purpose, and the real value emerges when they work together effectively to solve actual problems.

<div class="career-architecture">

```
┌─────────────────────────────────────────┐
│  Kubernetes (OVH / OpenStack)           │
│  ├─ Argo Workflows (batch pipelines)    │
│  ├─ Argo Events (data-driven triggers)  │
│  ├─ Helm (packaging)                    │
│  └─ Flux (GitOps reconciliation)        │
└─────────────────────────────────────────┘
                    ↕
┌─────────────────────────────────────────┐
│  Delivery & IaC                         │
│  ├─ GitHub Actions (CI/CD)              │
│  ├─ Terraform (multi-environment)       │
│  └─ AWS (secondary cloud, CDK/boto3)    │
└─────────────────────────────────────────┘
```
</div>

### 🐳 Containerization & Security Stack

Container security emerged as a natural extension of my infrastructure work when I began focusing on platform reliability and team productivity. Working with minimal base images has shown me that security practices can actually simplify operations - fewer vulnerabilities mean less time spent on patches and more predictable deployment cycles.

<div class="career-architecture">

```
┌──────────────┬───────────────┬────────────────┐
│   Security   │  Containers   │  Orchestration │
├──────────────┼───────────────┼────────────────┤
│ Prowler      │  Docker       │  Kubernetes    │
│ Trivy        │  Multi-stage  │  Argo Workflows│
│ zizmor       │  Chainguard   │  Argo Events   │
├──────────────┼───────────────┼────────────────┤
│ Keycloak /   │  Minimal      │  Helm / Flux   │
│ OIDC         │  base images  │  GitOps        │
└──────────────┴───────────────┴────────────────┘
```
</div>

### 🤖 AI-Assisted Engineering

A growing part of how I work is pairing with coding agents day to day - exploring unfamiliar codebases, drafting tests, and getting through the more mechanical parts of a refactor faster. I treat their output the way I treat my own first draft: useful, but nothing ships until I have read it, understood it, and can explain why each change is correct. Working this way has pushed me to be more deliberate about writing clear specifications and keeping a tight verification loop, not less.

## 🧭 Design & Delivery

A good part of my job doesn't show on the commit graph: working out what to build before building it, and how to change a system people already depend on without breaking it.

| Practice | What it looks like in my work |
|----------|-------------------------------|
| **Architecture decisions** | Architecture decision records and MVP breakdowns written before the code, with open questions left explicit for the team |
| **Capacity & data layout** | Capacity plans from measured throughput; chunk and shard layouts chosen from read benchmarks on the live data |
| **Standards** | STAC, Zarr/GeoZarr and CF conventions, checked across readers (GDAL, TiTiler, OpenLayers) |
| **Releases & versioning** | Automated semantic releases and pinned versions; the data-model version recorded in the catalogue; each data release tied to a tagged snapshot |
| **Production changes** | Dry runs and canaries before full production runs, run limits enforced inside the tool, and an undo path rehearsed before the big runs |

<br>

## 👥 Team Leadership & Enablement


> "The greatest good you can do for another is not just share your riches, but reveal to them their own." - _Benjamin Disraeli_


I don't think that leading small teams was something I set out to do, it kind of emerged from wanting to share what I'd learned and help others to grow. My experience in academia certainly helped me in developing a strong mentoring culture.

### Leadership Experience

Throughout my career, I've had opportunities to mentor and support team members:

**Current Practice (Development Seed)**
- Reviewing colleagues' and partners' pull requests in depth before release
- Writing runbooks and playbooks the team can reuse, for example on container hardening and on registering datacube releases
- Helping run eoAPI + STAC workshops, including prototyping isolated per-participant eoAPI stacks on Kubernetes for FOSS4G:UK 2026

**Previous Leadership (DWP)**
- Mentored four junior engineers through pair programming and knowledge sharing
- Regular debugging sessions that became teaching moments
- Wrote onboarding guides for new team members
- Created reusable Terraform modules and Docker templates encoding best practices
- Raised test coverage from 10% to 85% on two production web apps
- Implemented pre-commit hooks and CI/CD standards balancing guidance with flexibility

**Research Experience**
- Helped train PhD students and research staff in computational methods
- Helped plan and run OSNAP mooring cruises with international teams of 10+ people
- Mentored Master's students on research cruises and their thesis projects
- Contributed to the OceanGliders water-transformation task team
- Reviewed papers for JGR Oceans and Geophysical Research Letters, and research proposals

### Some Reflections on Technical Leadership

**Learning Through Collaboration**: Some of my most valuable moments happen when working alongside my teammates on challenging problems. Those debugging sessions often become mutual learning experiences where we both discover better approaches to error handling and system design.


**Freedom Through Structure**: I've found it interesting how clear technical guidelines can actually increase creativity. When the team doesn't have to worry about formatting or basic quality checks, I think it creates more mental space to focus on solving the actual problems at hand.


**From Solving to Enabling**: I'm gradually shifting from "I know how to fix this" to "How can we build systems so this problem becomes easier for everyone to solve?" When I built that Docker Compose environment to allow the team to run integration tests between our web application, graph database, and splunk server, it didn't just solve an immediate problem, it removed a recurring blocker for everyone.




### Current Focus Areas

- **Knowledge Sharing**: Contributing to documentation and learning resources for geospatial data engineering
- **Open Source Participation**: Engaging with communities building Earth observation infrastructure
- **Science to Software**: Turning scientific data and methods into tools and datasets other people use, from glider and mooring toolboxes in my oceanography years to analysis-ready satellite datacubes today




## 🎯 Core Competencies

The diagram below shows how I understand my professional development, with **Problem Solving** as "the driving force". 

The three branches reflect my career evolution: **Scientific Thinking** from research years where you learn to be systematic and question everything, **Engineering Practices** developed transitioning to software development, and **Team Leadership** emerging as I found sharing knowledge often more impactful than individual work. These areas reinforce each other: my research background helps me approach infrastructure methodically, engineering experience makes me a better mentor, and team work drives more systematic thinking.

The **Continuous Learning** foundation feels essential: every role change, technology, or colleague conversation adds to this framework. It's how I approach growth: staying curious, building on what I know, and helping others grow too.

<div class="career-architecture">

```
                     ┌─────────────────┐
                     │     PROBLEM     │
                     │     SOLVING     │
                     └─────────────────┘
                              │
         ┌────────────────────┼────────────────────┐
         │                    │                    │
 ┌───────▼──────┐     ┌───────▼───────┐     ┌──────▼──────┐
 │  SCIENTIFIC  │────>│  ENGINEERING  │────>│     TEAM    │
 │  THINKING    │     │  PRACTICES    │     │  LEADERSHIP │
 │              │     │               │     │             │
 │ • Systematic │     │ • Automation  │     │ • Mentoring │
 │ • Rigorous   │     │ • Security    │     │ • Pairing   │
 │ • Data-Driven│     │ • Scalability │     │ • Standards │
 └──────────────┘     └───────────────┘     └─────────────┘
        ▲                    ▲                    ▲
        └────────────────────┼────────────────────┘
                             │
                     ┌───────┴───────┐
                     │  CONTINUOUS   │
                     │   LEARNING    │
                     └───────────────┘
```

</div>
