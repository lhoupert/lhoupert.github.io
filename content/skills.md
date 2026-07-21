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

My decade working with oceanographic observations—processing data from underwater sensors, research vessels, and satellite altimetry—provided deep experience with large-scale scientific data workflows. This background translates directly to Earth observation infrastructure: both domains require robust data pipelines, quality control procedures, systematic metadata management, and cloud-optimized data formats.

| Domain | Experience & Approaches | Current Applications |
|--------|------------------------|---------------------|
| **Data Formats** | NetCDF, HDF5, GRIB → STAC, Zarr, COGs | Cloud-optimized geospatial formats |
| **Processing** | Time-series analysis, quality control, uncertainty quantification | Earth observation data pipelines |
| **Scale** | Datasets >200k observations, multi-platform integration | Terabyte-scale satellite imagery |
| **Metadata** | CF conventions, standardized vocabularies | STAC catalogs, searchable metadata |

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

Container security emerged as a natural extension of my infrastructure work when I began focusing on platform reliability and team productivity. Working with minimal, zero-CVE base images has shown me that security practices can actually simplify operations - fewer vulnerabilities mean less time spent on patches and more predictable deployment cycles.

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

## 👥 Team Leadership & Enablement


> "The greatest good you can do for another is not just share your riches, but reveal to them their own." - _Benjamin Disraeli_


I don't think that leading small teams was something I set out to do, it kind of emerged from wanting to share what I'd learned and help others to grow. My experience in academia certainly helped me in developing a strong mentoring culture.

### Leadership Experience

Throughout my career, I've had opportunities to mentor and support team members:

**Current Practice (Development Seed)**
- Contributing to collaborative engineering culture in distributed teams
- Sharing knowledge about geospatial data processing and cloud infrastructure
- Supporting open-source community participation

**Previous Leadership (DWP)**
- Led team of 2 junior engineers through pair programming and knowledge sharing
- Regular debugging sessions that became teaching moments
- Developed comprehensive onboarding guides reducing setup time from days to hours
- Created reusable Terraform modules and Docker templates encoding best practices
- Built testing strategies achieving 85% coverage implementation
- Implemented pre-commit hooks and CI/CD standards balancing guidance with flexibility

**Research Experience**
- Trained PhD students and research staff in computational methodologies
- Co-led oceanographic field campaigns coordinating 10+ team members
- Mentored early-career scientists in data analysis techniques

### Some Reflections on Technical Leadership

**Learning Through Collaboration**: Some of my most valuable moments happen when working alongside my teammates on challenging problems. Those debugging sessions often become mutual learning experiences where we both discover better approaches to error handling and system design.


**Freedom Through Structure**: I've found it interesting how clear technical guidelines can actually increase creativity. When the team doesn't have to worry about formatting or basic quality checks, I think it creates more mental space to focus on solving the actual problems at hand.


**From Solving to Enabling**: I'm gradually shifting from "I know how to fix this" to "How can we build systems so this problem becomes easier for everyone to solve?" When I built that Docker Compose environment to allow the team to run integration tests between our web application, graph database, and splunk server, it didn't just solve an immediate problem, it removed a recurring blocker for everyone.




### Current Focus Areas

- **Knowledge Sharing**: Contributing to documentation and learning resources for geospatial data engineering
- **Open Source Participation**: Engaging with communities building Earth observation infrastructure
- **Cross-Domain Translation**: Bridging scientific data processing and cloud-native engineering practices




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
