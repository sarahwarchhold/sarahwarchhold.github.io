---
layout: page
permalink: "/publications/"
title: "publications & talks"
description: ""
nav: true
nav_order: 4
post-header: true
bibtypes:
  - bibquery: "@inproceedings"
    text: "Conferences"
  - bibquery: "@misc"
    text: "Open Educational Resources"
  - bibquery: "@book"
    text: "Published"
---

{% for bibtype in page.bibtypes %}
  {% capture category_counter %}
    {% bibliography_count -f {{ site.scholar.bibliography }} -q {{ bibtype.bibquery }} %}
  {% endcapture %}

  <div style="counter-reset:bibitem {{ category_counter | plus:1 }}">
    <div class="publications">
      <h3 class="type">{{ bibtype.text }}</h3>
      {% bibliography -f {{ site.scholar.bibliography }} -q {{ bibtype.bibquery }} %}
    </div>
  </div>

{% endfor %}

