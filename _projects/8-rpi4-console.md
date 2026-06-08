---
layout: page
title: "RI One — Raspberry Pi 4 Retro Gaming Console"
description: "Custom-designed and 3D-printed Raspberry Pi 4 retro gaming console with a fully original case design. Published model on Printables — available for free community download."
img: assets/img/projects/rpi4-console.jpg
importance: 8
category: hardware
tags: [Raspberry Pi 4, Fusion 360, 3D Printing, RetroPie, Product Design]
github: https://www.printables.com/model/1417140-ri-one-rpi4-case
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
  <i class="fas fa-cube"></i> Download on Printables
</a>
{% endif %}

---

### Overview

The RI One is a custom-designed Raspberry Pi 4 console enclosure — designed from scratch in Autodesk Fusion 360, optimised for FDM printing, and published on Printables for the maker community. Runs RetroPie for multi-platform retro gaming.

---

### Design Details

- **CAD:** Autodesk Fusion 360 — fully parametric for RPi 4B form factor
- **Print:** PLA, Ender 3 V2 Neo — 0.2 mm layer height, 20% infill
- **Ports:** Cutouts for all RPi 4 I/O: USB-A ×4, USB-C power, HDMI ×2, Ethernet, 3.5mm audio, microSD slot
- **Ventilation:** Top-mounted passive channels accounting for RPi 4B thermal profile
- **Software:** RetroPie on Raspberry Pi OS Lite

---

### Community

Published at [printables.com/model/1417140](https://www.printables.com/model/1417140-ri-one-rpi4-case) — free download. Part of a broader interest in designing 3D-printable electronics enclosures with clean aesthetics and functional port access.
