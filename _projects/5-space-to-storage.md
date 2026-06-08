---
layout: page
title: "Space to Storage — Agricultural Satellite Data Platform"
description: "Next.js + FastAPI platform using satellite topography data to help farmers make data-driven decisions on crop selection, irrigation, and drainage. EPICS social-impact project, VIT Bhopal."
img: assets/img/projects/space-to-storage.jpg
importance: 5
category: software
tags: [Next.js, React, JavaScript, Tailwind CSS, FastAPI, Python, Satellite Data]
github: https://github.com/PlabanKr/space-to-storage-frontend
---

{% if page.tags %}
<p style="margin-bottom:0.4rem;">
{% for tag in page.tags %}
<span style="display:inline-block;background:var(--global-code-bg-color,#f0f0f0);color:var(--global-text-color,#333);border-radius:4px;padding:2px 9px;font-size:0.77rem;margin:2px 2px 2px 0;">{{ tag }}</span>
{% endfor %}
</p>
{% endif %}

{% if page.github %}
<a href="{{ page.github }}" target="_blank"
   style="display:inline-flex;align-items:center;gap:0.35rem;padding:6px 14px;background:#24292e;color:#fff;border-radius:5px;text-decoration:none;font-size:0.82rem;margin-bottom:0.75rem;">
  <i class="fab fa-github"></i> View on GitHub
</a>
{% endif %}

---

### Overview

Space to Storage is an agricultural optimisation platform built as a social-impact EPICS project at VIT Bhopal. The platform processes satellite topography and elevation data to help farmers make informed decisions about crop selection, irrigation strategy, drainage planning, and water storage — reducing reliance on costly trial-and-error farming decisions.

---

### Components

**Frontend:** Next.js + React + Tailwind CSS
- Interactive map for field boundary selection
- Satellite elevation data visualised on terrain overlay
- Recommendations panel with actionable crop/irrigation guidance

**Backend:** FastAPI (Python)
- Satellite data ingestion and processing pipeline
- Topographic analysis: elevation gradients, water flow simulation, drainage scoring
- Crop suitability scoring based on terrain profile

---

### Results

- Working end-to-end prototype demonstrated to faculty review panel
- Kazi's contribution: full Next.js frontend + FastAPI backend integration
- Platform designed for low-connectivity rural deployment (static pre-processing, low-bandwidth API)
