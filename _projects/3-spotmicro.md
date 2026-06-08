---
layout: page
title: "SpotMicro Quadruped Robot"
description: "Custom 3D-printed quadruped robot with web-based remote-control UI and full 12-servo gait implementation built from scratch. Final Year Project, VIT Bhopal (B.Tech CSE)."
img: assets/img/projects/spotmicro.jpg
importance: 3
category: robotics
tags: [ESP32-S3, Python, Fusion 360, 3D Printing, Servo Control, Gait, WebSocket]
github: https://frostkazi.github.io/SpotMicro
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
  <i class="fab fa-github"></i> Build Gallery
</a>
{% endif %}

---

### Overview

A simplified Boston Dynamics Spot-inspired quadruped robot — designed, 3D-printed, and programmed entirely from scratch as my Final Year Project at VIT Bhopal. The robot features a custom Fusion 360 frame, full quadruped gait implementation coordinating 12 servos, and a web-based UI for remote control with computation offloaded via ESP32-S3.

---

### Hardware Components

- **Microcontroller:** ESP32-S3 (dual-core, Wi-Fi + BT, handles servo coordination + web server)
- **Servos:** 12× MG996R digital servos (3 per leg: hip, shoulder, knee)
- **Frame:** Custom 3D-printed PLA (Fusion 360, printed on Ender 3 V2 Neo)
- **Power:** 2S LiPo 7.4V → buck converter → 5V rail for ESP32 + servos
- **Control:** Browser-based WebSocket UI served from the ESP32-S3

---

### Control → Gait → State Machine

Each leg has 3 DOF. All 12 servos are driven via PWM from the ESP32-S3. Joint angles are computed via inverse kinematics from desired foot position in leg-local coordinates.

**Gait sequences:**
- **Trot:** Diagonal leg pairs move simultaneously (FL+RR, FR+RL)
- **Creep:** One leg at a time for maximum stability at low speed
- **Stand / Sit:** Pre-computed joint angle arrays for stable transitions

**Web UI State Machine:**
```
IDLE  →  STAND  →  WALK (FWD / BWD / TURN L / TURN R)
               ↓
             SIT
```

All state transitions triggered via WebSocket commands from the browser — latency < 50 ms over local Wi-Fi.

---

### Build Documentation

Full step-by-step gallery at [frostkazi.github.io/SpotMicro](https://frostkazi.github.io/SpotMicro):
- Parts inventory and BOM
- Printed component assembly sequence
- Servo calibration and joint angle tuning
- Internal wiring and cable routing
- Video log of first steps and gait testing

---

### Results

- 12-servo gait successfully implemented from scratch
- Web-based remote control working at < 50 ms latency
- Full build documented: 30+ photos + video log

### Future Work

- ROS2 integration for navigation and SLAM
- ML-based gait optimisation replacing hand-tuned IK
- Computer vision obstacle avoidance (depth camera)
