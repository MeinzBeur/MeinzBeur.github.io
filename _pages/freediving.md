---
layout: page
title: Freediving
permalink: /freediving/
description: Theory lessons for freediving courses
nav: true
nav_order: 7
display_categories: [CMAS*** Freediving, CMAS* Apnea] 
horizontal: false
---

<!-- <h1>Freediving</h1>

<div class="freediving">
  {% assign sorted_freediving = site.freediving | sort: "importance" %}
  {% for freedive in sorted_freediving %}
    <div class="freedive">
      <h2><a href="{{ freedive.url }}">{{ freedive.title }}</a></h2>
      <p>{{ freedive.excerpt }}</p>
    </div>
  {% endfor %}
</div> -->

<!-- pages/freediving.md -->
<div class="freediving">
{% if site.enable_freedive_categories and page.display_categories %}
  <!-- Display categorized freediving -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_freediving = site.freediving | where: "category", category %}
  {% assign sorted_freediving = categorized_freediving | sort: "importance" %}
  <!-- Generate cards for each freedive -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for freedive in sorted_freediving %}
      {% include freediving_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for freedive in sorted_freediving %}
      {% include freediving.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display freediving without categories -->

{% assign sorted_freediving = site.freediving | sort: "importance" %}

  <!-- Generate cards for each freedive -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for freedive in sorted_freediving %}
      {% include freediving_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for freedive in sorted_freediving %}
      {% include freediving.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
