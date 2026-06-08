---
layout: page
title: projects
permalink: /projects/
description: Engineering projects in robotics, autonomous systems, and embedded hardware.
nav: true
nav_order: 2
horizontal: false
---

<div class="projects">
  {% assign sorted_projects = site.projects | sort: "importance" %}
  {% for project in sorted_projects %}
    {% include projects.liquid %}
  {% endfor %}
</div>
