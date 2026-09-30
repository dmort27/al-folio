---
layout: page
permalink: /publications/
title: publications
description: Publications by year in reverse chronological order.
years: [2026, 2025, 2024, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2013, 2012, 2011, 2004, 2003, 2002]
nav: true
---

<div class="publications">

{% for y in page.years %}
  <h3 class="year">{{y}}</h3>
  {% bibliography -f drmpubs -q @*[year={{y}}]* %}
{% endfor %}

</div>
