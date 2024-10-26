---
layout: page
permalink: /publications/
title: publications
description: publications by categories in reversed chronological order.
years: [2024,2023, 2022, 2021, 2020]
nav: true
nav_order: 1
---
See my full publication list in [google scholar](https://scholar.google.com/citations?user=-zSd9V0AAAAJ&hl=en).
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>