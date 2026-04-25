---
layout: page
title: projects
permalink: /projects/
description: Selected leadership, engineering, and competition projects.
nav: false
nav_order: 3
display_categories: [research, engineering, leadership]
horizontal: false
---

<div class="projects">
{% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category | sort: "importance" %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in categorized_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
{% endfor %}
</div>
