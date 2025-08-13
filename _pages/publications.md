---
layout: page
permalink: /publications/
title: Publications
description: An up-to-date list is available on <a href="https://scholar.google.com/citations?hl=en&user=Jp41q6AAAAAJ" style="color:#0076df;" target="_blank">Google Scholar</a>.
nav: true
nav_order: 1
---
{% assign sorted_papers = site.scholar.bibliographies.papers.entries | sort: 'year' | reverse %}
{% assign page.years = sorted_papers | map: 'year' | uniq %}

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

<h2>Preprints</h2>

{% bibliography -f preprints %}

<h2>Conference &amp; Journal Articles</h2>
{% for y in page.years %}
  <h3 class="year">{{y}}</h3>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

<h2>Technical Reports &amp; Short Papers</h2>

{% bibliography -f reports %}

</div>
