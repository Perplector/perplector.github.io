---
permalink: /projects/
title: "Projects"
layout: collection
collection: projects
entries_layout: grid
classes: wide

header:
  overlay_image: /assets/images/wheat_banner.jpg
---

{% for post in site.projects %}
  {% include archive-single.html %}
{% endfor %}