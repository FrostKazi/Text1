---
layout: page
title: "Robotic Arm — Vision-Guided Manipulation"
description: "Multi-axis 3D-printed robotic arm with inverse kinematics and OpenCV-based vision-guided manipulation. Built with Fusion 360, Arduino, and ROS. Currently in development."
img: assets/img/projects/robotic-arm.jpg
importance: 7
category: robotics
tags: [Fusion 360, Arduino, ROS, Python, OpenCV, 3D Printing, Inverse Kinematics]
---

{% if page.tags %}
<p style="margin-bottom:0.4rem;">
{% for tag in page.tags %}
<span style="display:inline-block;background:var(--global-code-bg-color,#f0f0f0);color:var(--global-text-color,#333);border-radius:4px;padding:2px 9px;font-size:0.77rem;margin:2px 2px 2px 0;">{{ tag }}</span>
{% endfor %}
</p>
{% endif %}

<p style="display:inline-flex;align-items:center;gap:0.4rem;padding:4px 12px;
   border:1px solid #e67e22;color:#e67e22;border-radius:5px;font-size:0.82rem;margin-bottom:1rem;">
  <i class="fas fa-tools fa-sm"></i> In Progress
</p>

---

### Overview

A multi-axis 3D-printed robotic arm currently under development — extending experience with servo-driven systems from SpotMicro into a structured manipulator platform. Target: full inverse kinematics, vision-guided pick-and-place using OpenCV, and ROS integration for trajectory planning.

---

### Design Targets

- **DOF:** 5–6 axis (shoulder, elbow, wrist pitch/roll/yaw, gripper)
- **Actuation:** Servo-driven (MG996R + DS3218 for high-torque joints)
- **Frame:** Fully 3D-printed PLA + PETG hybrid (Fusion 360 → Ender 3 V2 Neo)
- **Control:** Arduino for low-level servo PWM → ROS node for high-level commands
- **Vision:** OpenCV colour-based detection → coordinate transform → IK solver

---

### Current Status

- [x] Fusion 360 full arm design complete
- [x] Base + shoulder assembly printed and assembled
- [ ] Elbow and wrist assembly in progress
- [ ] IK solver (Python, DH parameters)
- [ ] ROS node integration
- [ ] OpenCV vision-guided target tracking
