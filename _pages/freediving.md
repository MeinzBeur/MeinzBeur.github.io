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

<h1>Freediving</h1>

<div class="freediving">
  {% assign sorted_freediving = site.freediving | sort: "importance" %}
  {% for freedive in sorted_freediving %}
    <div class="freedive">
      <h2><a href="{{ freedive.url }}">{{ freedive.title }}</a></h2>
      <p>{{ freedive.excerpt }}</p>
    </div>
  {% endfor %}
</div>

