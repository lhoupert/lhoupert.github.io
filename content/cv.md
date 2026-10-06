---
title: "CV"
date: 2026-10-06
layout: simple
---

I started in physical oceanography, where I spent about ten years (2010–2021) observing the ocean with gliders, moorings and research ships, writing processing code and publishing open datasets so others could use those observations. I then moved into software and cloud engineering, and since November 2025 I've been building Earth observation data systems at Development Seed.

If you prefer a more theatrical version, co-written with [Claude](https://claude.ai) in 2025, it's here: _[Loïc's journey](/journey)_

## Career Evolution Timeline

<div class="career-timeline">

### 🌍 **Cloud Engineer** `2025 → Present`
*Development Seed | Remote, UK*

**Earth observation data systems, from design to production**
- Wrote the first architecture decision record and MVP plan for onboarding EUMETSAT data into the Destination Earth Data Lake, then built a large part of the chain that turns satellite products into HEALPix Zarr and Icechunk datacubes, including the MSG SEVIRI, MTG FCI and first Sentinel-3 OLCI cubes, with STAC metadata and quickstart notebooks for users
- Turned throughput benchmarks into a capacity plan for the MVP, and chose datacube chunk layouts from read benchmarks on the live stores
- Worked on the Sentinel-to-GeoZarr conversion and STAC registration pipelines for ESA's EOPF Sentinel Zarr Explorer (Kubernetes, Argo Workflows), and built most of the storage lifecycle and retention automation
- Built a Sentinel-1 radiometric terrain correction MVP that produced per-tile GeoZarr datacubes over France and the Alps, and contributed its data model and STAC builders to the open-source eopf-geozarr library
- Added STAC validation before publishing and GeoZarr conformance checks across readers (GDAL, TiTiler, OpenLayers), reporting validator gaps upstream
- Started Development Seed's supply-chain security effort: a reusable security-auditing GitHub Action and pinning/Dependabot fixes across Development Seed and community geospatial repositories
- Upstream contributions to OpenLayers (GeoZarr dimension selection) and fixes in fsspec and the STAC/eoAPI tooling; talks at FOSS4G Europe and UKEO 2026, and helped run an eoAPI + STAC workshop

*The research years still help: when Sentinel-1 output looked 47 km off, the cause was a geoid grid stored in 0–360° longitude.*

---

### 🚀 **Senior Cyber Platform Engineer** `2023 → 2025`
*Department for Work and Pensions - Digital | Remote, UK*

**Secure container platform for cyber data science**
- Co-architected and built a container platform on AWS (ECS Fargate, Terraform modules) used to deploy the analytics and AI applications that cyber data scientists and analysts rely on
- Added automated security scanning (Semgrep, KICS, Trivy) to the CI/CD pipelines
- Moved container images to minimal Chainguard base images
- Increased deployment frequency from monthly to weekly through CI/CD automation
- Raised test coverage from 10% to 85% on two production web apps, with a containerised integration-test environment
- Mentored four junior engineers through pair programming and knowledge sharing

---

### 💻 **Software Engineer** `2022 → 2023`
*Department for Work and Pensions - Digital | Newcastle, UK*

**Machine learning prototypes in a regulated environment**
- Built the machine-learning component of a prototype that classifies handwritten correspondence: a zero-shot classifier (BART-large-MNLI) whose candidate labels I tuned against test datasets I built, on AWS SageMaker, deployed with AWS CDK in TypeScript
- Built container-based serverless applications with Python and AWS Lambda, with Docker-based CI
- Helped establish Python coding standards across development teams

---

### 🔧 **R&D Software Engineer** `2021 → 2022`
*OSE Engineering | France (remote)*

**Python libraries and a product prototype**
- Packaged vehicle-routing optimisation methods into Python libraries, with documentation and tutorials, for a delivery-robot fleet management prototype
- Built the full-stack prototype (Django, with live data collection and visualisation; WebSocket/WebRTC real-time communication handling 20+ concurrent robot connections) and its Docker development environment
- Wrote the team's development best-practice guides

---

### 🌊 **Research Scientist** `2019 → 2021`
*National Oceanography Centre | Southampton, UK*

**Subpolar North Atlantic circulation and transport**
- Published the first four years of continuous North Atlantic Current volume transport measurements from the OSNAP mooring array in the Rockall Trough (JGR Oceans, 2020), using an ocean reanalysis to fill a gap at the shelf edge. Quantified the uncertainty with Monte Carlo propagation of instrument errors and with sampling tests on repeat ship sections, and released the time series openly; a 2026 study by the SAMS and NOC team builds on it for a decade-long record
- Co-authored a study of Nordic Seas overturning, and the associated heat flux, over the past 70–100 years (GRL, 2020), and contributed to EU Blue-Action and ATLAS project reports, including the glider volume-transport section of a Blue-Action report on heat transport toward the Arctic
- Extended the OSNAP mooring processing toolbox to NOC's Iceland Basin moorings and co-created the resulting BODC dataset
- Moved my analysis to Python (xarray, pandas), with reproducible and containerised workflows (conda, Docker, Binder, CI)
- Helped train PhD students and research staff in computational methods

---

### 🔬 **Research Project Scientist** `2014 → 2018`
*Scottish Association for Marine Science | Oban, UK*

**UK-OSNAP: gliders and moorings in the eastern subpolar North Atlantic**
- Helped plan and run SAMS's part of OSNAP on the eastern boundary (Rockall Trough moorings and Seaglider missions over the Rockall Plateau), from the cruises to the archived data
- Co-planned and co-piloted nine Seaglider missions; sailed on four OSNAP mooring cruises (2015–2018) with international teams, ran calibration casts for the moored CTD sensors against the ship's CTD, and edited or co-authored the 2014–2017 cruise reports
- Wrote a MATLAB toolbox for glider processing, quality control and gridding; led the adaptation of the RAPID-MOC mooring processing toolbox for OSNAP and maintained it (SAMS still uses it on its mooring cruises)
- Published the UK-OSNAP glider datasets (near-real-time and quality-controlled) at the British Oceanographic Data Centre and co-created the Rockall Trough mooring datasets; these data went into the array-wide OSNAP overturning results I co-authored (Lozier et al. 2019, Science)
- Quantified North Atlantic Current volume transport over the Rockall Plateau from 16 repeat glider sections, with Monte Carlo uncertainty estimates for each section (JGR Oceans, 2018)
- Across my research years: 12 research cruises in the North Atlantic and Mediterranean (2010–2018), about 200 days at sea

---

### 📚 **PhD Fellow & Postdoc** `2010 → 2014`
*CNRS / Université de Perpignan & LOCEAN Paris | France*

**Mediterranean deep convection and upper-ocean heat storage**
- Merged 13 hydrographic databases into a quality-controlled set of more than 140,000 temperature profiles, and published the resulting Mediterranean climatology as an open dataset with a DOI (Progress in Oceanography, 2015)
- Analysed 2007–2013 observations of open-ocean deep convection in the north-western Mediterranean (JGR Oceans, 2016)
- Helped run the LION deep-convection mooring and wrote its sensor intercalibration report
- Postdoc at LOCEAN: quantified the space and time scales of winter mixing with statistical and wavelet methods
- Took part in Mediterranean research cruises with gliders, moorings and ship-based measurements

</div>

## Selected publications and open data

The full list is on [Google Scholar](https://scholar.google.com/citations?user=10K7fIYAAAAJ&hl=en) and [ORCID](https://orcid.org/0000-0001-8750-5631).

**First-author papers**
- Houpert, L., et al. (2020). Observed variability of the North Atlantic Current in the Rockall Trough from 4 years of mooring measurements. *JGR: Oceans*. [doi:10.1029/2020JC016403](https://doi.org/10.1029/2020JC016403)
- Houpert, L., et al. (2018). Structure and transport of the North Atlantic Current in the eastern subpolar gyre from sustained glider observations. *JGR: Oceans*. [doi:10.1029/2018JC014162](https://doi.org/10.1029/2018JC014162)
- Houpert, L., et al. (2016). Observations of open-ocean deep convection in the northwestern Mediterranean Sea: Seasonal and interannual variability of mixing and deep water masses for the 2007–2013 period. *JGR: Oceans*. [doi:10.1002/2016JC011857](https://doi.org/10.1002/2016JC011857)
- Houpert, L., et al. (2015). Seasonal cycle of the mixed layer, the seasonal thermocline and the upper-ocean heat storage rate in the Mediterranean Sea derived from observations. *Progress in Oceanography*, 132, 333–352. [doi:10.1016/j.pocean.2014.11.004](https://doi.org/10.1016/j.pocean.2014.11.004)

**Close collaborations**
- Durrieu de Madron, X., Houpert, L., et al. (2013). Interaction of dense shelf water cascading and open-sea convection in the northwestern Mediterranean during winter 2012. *Geophysical Research Letters*. [doi:10.1002/grl.50331](https://doi.org/10.1002/grl.50331)
- Somot, S., Houpert, L., et al. (2018). Characterizing, modelling and understanding the climate variability of the deep water formation in the North-Western Mediterranean Sea. *Climate Dynamics*. [doi:10.1007/s00382-016-3295-0](https://doi.org/10.1007/s00382-016-3295-0)
- Koman, G., Johns, W. E., Houk, A., Houpert, L., & Li, F. (2022). Circulation and overturning in the eastern North Atlantic subpolar gyre. *Progress in Oceanography*. [doi:10.1016/j.pocean.2022.102884](https://doi.org/10.1016/j.pocean.2022.102884)

**OSNAP and ocean-observing programme papers**
- Lozier, M. S., et al. (2019). A sea change in our view of overturning in the subpolar North Atlantic. *Science*. [doi:10.1126/science.aau6592](https://doi.org/10.1126/science.aau6592)
- Li, F., et al. (2021). Subpolar North Atlantic western boundary density anomalies and the Meridional Overturning Circulation. *Nature Communications*. [doi:10.1038/s41467-021-23350-2](https://doi.org/10.1038/s41467-021-23350-2)
- Lozier, M. S., et al. (2017). Overturning in the Subpolar North Atlantic Program: A new international ocean observing system. *Bulletin of the American Meteorological Society*. [doi:10.1175/BAMS-D-16-0057.1](https://doi.org/10.1175/BAMS-D-16-0057.1)
- Testor, P., et al. (2019). OceanGliders: A component of the integrated GOOS. *Frontiers in Marine Science*. [doi:10.3389/fmars.2019.00422](https://doi.org/10.3389/fmars.2019.00422)

**Open data, code and reports**
- Gridded climatology of the mixed layer, seasonal thermocline and upper-ocean heat storage rate for the Mediterranean Sea, 1969–2013 (SEANOE). [doi:10.17882/46532](https://doi.org/10.17882/46532)
- UK OSNAP delayed-mode glider dataset, 2014–2018 (BODC). [doi:10.5285/79fdab65-0ce9-56ef-e053-6c86abc08912](https://doi.org/10.5285/79fdab65-0ce9-56ef-e053-6c86abc08912)
- OSNAP mooring processing toolbox (MATLAB), now maintained by SAMS: [ScotMarPhys/m_moorproc_toolbox](https://github.com/ScotMarPhys/m_moorproc_toolbox)
- Glider processing and quality-control toolbox (MATLAB): [lhoupert/m_oceanglider](https://github.com/lhoupert/m_oceanglider)
- Sentinel-1 RTC GeoZarr data model and STAC builders in [eopf-geozarr](https://github.com/EOPF-Explorer/data-model) (contributor)
- Houpert, L. (2014). Technical report on the intercalibration of the sensors on the LION mooring line. [doi:10.13140/RG.2.1.4787.3044](https://doi.org/10.13140/RG.2.1.4787.3044)
