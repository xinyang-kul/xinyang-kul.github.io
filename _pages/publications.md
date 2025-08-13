---
layout: page
permalink: /publications/
title: Publications
description: An up-to-date list is available on <a href="https://scholar.google.com/citations?hl=en&user=Jp41q6AAAAAJ" style="color:#0076df;" target="_blank">Google Scholar</a>.
nav: true
nav_order: 1
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

<h1>preprints</h1>

{% bibliography -f preprints %}

<h1>conference &amp; journal articles</h1>

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

<h1>technical reports &amp; short papers</h1>

{% bibliography -f reports %}

</div>
