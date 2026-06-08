---
layout: page
title: "RC AeroBoat — Water Pollution Combat Drone Boat"
description: "1st Runner-Up nationally at Robothon 2022. RC boat using above-water drone propulsion for surface navigation, carrying a payload release mechanism for pollution-absorbent material deployment."
img: assets/img/projects/rc-aeroboat.jpg
importance: 6
category: hardware
tags: [Arduino, RC, Brushless Motors, ESC, Fabrication, Embedded Systems]
---

{% if page.tags %}
<p style="margin-bottom:0.4rem;">
{% for tag in page.tags %}
<span style="display:inline-block;background:var(--global-code-bg-color,#f0f0f0);color:var(--global-text-color,#333);border-radius:4px;padding:2px 9px;font-size:0.77rem;margin:2px 2px 2px 0;">{{ tag }}</span>
{% endfor %}
</p>
{% endif %}

---

### Overview

The RC AeroBoat was built for the Robothon 2022 national competition at VIT Bhopal on the theme of water pollution combat. The design repurposes aerial drone propulsion (brushless motors with 5" props) for surface thrust, mounted on a custom-fabricated hull. The boat carries a servo-actuated payload release mechanism for deploying pollution-absorbing material on water surfaces.

**Awarded 1st Runner-Up nationally at Robothon 2022.**

---

### Hardware Components

- **Propulsion:** 2× brushless motors (5" props) + 30A ESCs (drone components repurposed for surface thrust)
- **Control:** Arduino Mega + FlySky FS-i6 RC receiver (6-channel)
- **Hull:** Custom-fabricated fibreglass + foam composite — optimised for bow clearance and static stability
- **Payload:** Servo-actuated hatch for pollution-absorbent material deployment
- **Power:** 3S LiPo 11.1V

---

### Results

- **1st Runner-Up nationally — Robothon 2022** (VIT Bhopal Robotics Club)
- Successful water navigation + payload release demonstrated in competition
- Handling tested in controlled pool environment prior to competition day
