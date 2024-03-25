---
page_id: publications
layout: page
permalink: /publications/
title: Publication
description: 
nav: true
nav_order: 3
---

\* Equal Contribution 

† Corresponding Author

<!-- _pages/publications.md -->
<div class="publications">

{% for y in page.years %}
  <div class="col-sm-1 align-self-end mt-2 p-0 pr-1">
      <h2 class="bibliography-year">{{y}}</h2>
  </div>
  <div class="row m-0 p-0" style="border-bottom: 1px solid #ddd;">
    <div class="col-sm-11 p-0">
      {% bibliography -f papers -q @*[year={{y}}]* %}
    </div>
  </div>
{% endfor %}

</div>
