---
layout: page
title: projects
permalink: /
nav: true
nav_order: 1
---

<div class="projects-grid">
  {% assign sorted_projects = site.projects | sort: "importance" %}
  {% for project in sorted_projects %}
    {% include projects.liquid %}
  {% endfor %}
</div>
