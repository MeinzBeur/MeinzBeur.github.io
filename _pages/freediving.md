---
layout: page
title: Freediving
permalink: /freediving/
description: Theory lessons for freediving courses
nav: true
nav_order: 3
display_categories: [CMAS*** Freediving] # work, fun, 
horizontal: false
---

<!-- pages/freediving.md -->
<div class="freediving">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized freediving -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_freediving = site.freediving | where: "category", category %}
  {% assign sorted_freediving = categorized_freediving | sort: "importance" %}
  <!-- Generate cards for each freediving -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_freediving %}
      {% include freediving_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_freediving %}
      {% include freediving.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display freediving without categories -->

{% assign sorted_freediving = site.freediving | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_freediving %}
      {% include freediving_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_freediving %}
      {% include freediving.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
