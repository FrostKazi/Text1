---
layout: page
title: about
permalink: /
nav: true
nav_order: 1
---

<div style="max-width:800px; margin-bottom:2.5rem;">

<h2 style="font-size:1.85rem; font-weight:700; margin-bottom:0.2rem;">Kazi Abdul Baset</h2>
<p style="opacity:0.6; margin-bottom:1.1rem; font-size:0.95rem;">
  Robotics Engineer &middot; Embedded Systems &middot; Maker &amp; Entrepreneur &mdash; Brighton, UK
</p>

<p style="font-size:0.96rem; line-height:1.85;">
MSc Robotics &amp; Autonomous Systems at the University of Sussex
(<strong>John Kinghorn Scholar</strong> &mdash; £10,000 merit award).
Research: <em>Virtual Buffer</em> &mdash; vision &amp; radar sensor fusion for semi-autonomous train coupling,
achieving <strong>~3 cm positional accuracy</strong> without accessing proprietary rail systems.
Previously: SAE motorsport nationally ranked (AIR 1 Cost Report, ATVC 2024),
<strong>HackSussex 2026 Overall Grand Prize Winner</strong>,
self-funded 3D printing business recovered from scratch.
Over a decade of self-driven building &mdash; RC aircraft &times;7 fixed-wing &amp; &times;5 quadcopters,
quadruped robots, embedded systems from age 10.
</p>

<p style="margin-top:1.3rem;">
  <a href="mailto:amankazi2003@gmail.com"
     style="display:inline-flex;align-items:center;gap:0.3rem;padding:5px 13px;
            border:1px solid currentColor;border-radius:5px;text-decoration:none;
            font-size:0.82rem;opacity:0.75;margin:3px;">
    <i class="fas fa-envelope fa-sm"></i> Email
  </a>
  <a href="https://github.com/FrostKazi" target="_blank"
     style="display:inline-flex;align-items:center;gap:0.3rem;padding:5px 13px;
            border:1px solid currentColor;border-radius:5px;text-decoration:none;
            font-size:0.82rem;opacity:0.75;margin:3px;">
    <i class="fab fa-github fa-sm"></i> GitHub
  </a>
  <a href="https://linkedin.com/in/kazi-abdul-baset-ba7114242" target="_blank"
     style="display:inline-flex;align-items:center;gap:0.3rem;padding:5px 13px;
            border:1px solid currentColor;border-radius:5px;text-decoration:none;
            font-size:0.82rem;opacity:0.75;margin:3px;">
    <i class="fab fa-linkedin fa-sm"></i> LinkedIn
  </a>
  <a href="{{ '/cv/' | relative_url }}"
     style="display:inline-flex;align-items:center;gap:0.3rem;padding:5px 13px;
            border:1px solid currentColor;border-radius:5px;text-decoration:none;
            font-size:0.82rem;opacity:0.75;margin:3px;">
    <i class="fas fa-file-alt fa-sm"></i> CV / Resume
  </a>
</p>

</div>

---

<div class="projects">
  {% assign sorted_projects = site.projects | sort: "importance" %}
  {% for project in sorted_projects %}
    {% include projects.liquid %}
  {% endfor %}
</div>
