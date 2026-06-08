---
layout: page
title: "Smart Parking System — Automated ANPR & Billing"
description: "Full-stack automated parking management using computer vision ANPR on entry/exit. MySQL billing, live Streamlit dashboard. Reduced manual effort ~90%, billing time ~50%. VIT Bhopal Project Exhibition."
img: assets/img/projects/smart-parking.jpg
importance: 4
category: software
tags: [Python, OpenCV, pytesseract, cvzone, MySQL, Streamlit, OCR, ANPR]
github: https://github.com/jangirsamarth/parking-management-system-using-CV
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

A full-stack automated parking management system that eliminates manual entry/exit logging. Cameras at barriers detect vehicles, perform Automatic Number Plate Recognition (ANPR) via OCR, record timestamps in MySQL, and auto-calculate billing fees on exit. A live Streamlit dashboard shows real-time feeds and revenue analytics.

Presented at VIT Bhopal Project Exhibition I (3rd Semester).

---

### Components

- **Computer Vision:** OpenCV + cvzone for frame pre-processing and ROI extraction
- **OCR:** pytesseract (Tesseract 5.x) for licence plate text recognition
- **Database:** MySQL — entry/exit timestamps, fee calculation, vehicle log
- **Dashboard:** Streamlit — live camera feed, occupancy map, billing analytics
- **Hardware:** Standard USB cameras (IP camera-compatible)

---

### Pipeline → ANPR → Billing

```
Camera Frame
      ↓
Pre-process (grayscale → threshold → morphological ops)
      ↓
Contour detection → Licence plate ROI
      ↓
pytesseract OCR → Plate number string
      ↓
MySQL: INSERT / UPDATE record (entry / exit + timestamp)
      ↓
Fee = (exit_time - entry_time) × rate_per_hour
      ↓
Streamlit dashboard refresh
```

---

### Results

| Metric | Result |
|--------|--------|
| Manual effort reduction | **~90%** |
| Billing process speedup | **~50%** |
| OCR accuracy | > 85% on clean plates |
| Real-time latency | < 200 ms per frame |
