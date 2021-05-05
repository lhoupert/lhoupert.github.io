---
layout: archive
author_profile: true
title: Code
permalink: /code/
gallery:
  - image_path: /assets/images/fig11.png
  - image_path: /assets/images/fig22.png
---

*This section is under development...*

You can browse through my current projects on [GitHub](https://github.com/lhoupert).

## EEL project

During my previous position, I worked with the [Extended Ellett Line (EEL)](https://projects.noc.ac.uk/ExtendedEllettLine/) data. You can access the code I used to analyse and visualise the data on my [github repository](https://github.com/lhoupert/analysis_eel_data). You will find some useful bit of code to plot maps using [*cartopy*](https://scitools.org.uk/cartopy/docs/latest/), hydrographic sections using [*matplotlib*](https://matplotlib.org/), or manipulate multi-dimensional array using [xarray](http://xarray.pydata.org/en/stable/).

{% include gallery %}

## HoloViz and Panel
The notebook [holoview/02-lh-holoview_2_gridded_section.ipynb](https://github.com/lhoupert/analysis_eel_data/blob/master/notebooks/holoview/02-lh-holoview_2_gridded_section.ipynb) shows how to use [HoloViews](http://holoviews.org/) and [Panel](https://panel.holoviz.org/) to display an <a href="/assets/html/02_section_panel_double_selector_v3_vweb.html" target="_blank">interactive section of the EEL data</a>.

<section id='holview_sec' style="background-color: white">
  <iframe allowtransparency="true" src="/assets/html/02_section_panel_double_selector_v3_vweb.html" height="620px" width="100%" style="border:none;"></iframe>
</section>

<br>

## Folium

Recently, I started using [Folium](https://python-visualization.github.io/folium/) to visualise python data on [Leaflet maps](https://leafletjs.com/).

<iframe src="/assets/html/maps_ocean.html" height="400px" width="100%" style="border:none;"></iframe>
