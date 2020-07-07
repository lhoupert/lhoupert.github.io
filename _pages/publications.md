---
author_profile: true
layout: archive
title: Publications
permalink: /pubs/
toc: false
toc_sticky: true
toc_label: " "
toc_icon: "file-alt"
---

{% include figure image_path="/assets/images/dunst.jpg" alt="" %}

## Preprint Articles
{% for paper in site.data.preprint %}
+ {{ paper.num }}  &nbsp;  {{ paper.authors }}, {{paper.title}}, {{paper.journal}}, {{paper.year}}{% if paper.doi %}, [{{paper.doi}}]({{ paper.doilink }})  {% endif %}{% endfor %}

<br>
## Peer-reviewed Articles
{% for paper in site.data.publis %}
+ {{ paper.num }}  &nbsp;  {{ paper.authors }}, {{paper.title}}, {{paper.journal}}, {{paper.year}}{% if paper.doi %}, [{{paper.doi}}]({{ paper.doilink }})  {% endif %}{% endfor %}

Link to [Web of Science](https://publons.com/mashlets?el=badgeCont599&rid=Y-5796-2019)

<!-- ## Presentations
#### Talks


#### Poster
-->
<!--
## Preprint Articles
{% for paper in site.data.preprint %}
- {{ paper.authors }}, {{paper.title}}, {{paper.journal}}, {{paper.year}}{% if paper.doi %}, [link]({{ paper.doi }}){% endif %}{% endfor %}

## Peer-reviewed Articles
{% for paper in site.data.publications %}
+ {{ paper.authors }}, {{paper.title}}, {{paper.journal}}, {{paper.year}}{% if paper.doi %}, [link]({{ paper.doi }}){% endif %}{% endfor %}

## Talks
{% for talk in site.data.talks %}
+ {{ talk.authors }}, {{talk.title}}, {{talk.event}}, {{talk.location}}, {{talk.date}}{% if talk.doi %}, [link]({{ talk.doi }}){% endif %}{% if talk.path %}, [pdf]({{ talk.path }}) {% endif %}{% endfor %}

## Posters
{% for poster in site.data.posters %}
+ {{ poster.authors }}, {{poster.title}}, {{poster.event}}, {{poster.location}}, {{poster.date}}{% if poster.doi %}, [link]({{ poster.doi }}){% endif %}{% if poster.path %}, [pdf]({{ poster.path }}) {% endif %}{% endfor %} -->
