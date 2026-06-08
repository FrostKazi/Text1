---
layout: page
title: "Virtual Buffer — Vision & Radar Sensor Fusion for Train Coupling"
description: "Non-invasive bolt-on system for semi-autonomous train coupling. ChArUco 6-DOF pose estimation fused with Doppler mmWave radar via custom 1D Kalman filter. ~3 cm accuracy at 50–230 cm range. MSc Dissertation, University of Sussex."
img: assets/img/projects/virtual-buffer.jpg
importance: 1
category: research
tags: [Python, OpenCV, Kalman Filter, Raspberry Pi 4, mmWave Radar, Sensor Fusion, ChArUco]
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

Virtual Buffer is a non-invasive, bolt-on sensing system that provides real-time distance and 6-DOF alignment data for semi-autonomous train coupling — **without accessing any proprietary train control systems**. Inspired by NASA spacecraft docking procedures, the system fuses two independent sensor modalities: ChArUco marker-based computer vision for close-range pose estimation, and Doppler mmWave radar for ground-speed measurement. A custom 1D Kalman filter fuses both streams into a single reliable state estimate.

This is my MSc Dissertation at the University of Sussex, directly supporting the UK/EU **Digital Automatic Coupler (DAC)** railway migration programme — enabling trains to couple semi-autonomously for the first time.

---

### Hardware Components

- **Compute:** Raspberry Pi 4B (4 GB RAM, Ubuntu 22.04)
- **Vision:** USB webcam (global shutter upgrade planned)
- **Radar:** PCR 60 GHz Doppler mmWave radar module
- **Fiducial Marker:** Custom-printed ChArUco board (ArUco + checkerboard hybrid for sub-pixel corner accuracy)
- **Mounting:** Bolt-on front coupler bracket — zero modification to train required

---

### Architecture → State Machine → Sensor Fusion

The system runs a 5-state hysteresis state machine controlled by EMA-smoothed sensor output:

```
APPROACH  →  WARNING  →  STOP & EXTEND  →  COUPLING  →  CONTACT CONFIRMED
    ↑_________________________ABORT_________________________________|
```

| State | Trigger Distance | Action |
|-------|-----------------|--------|
| `APPROACH` | > 230 cm | Radar primary; monitor speed |
| `WARNING` | 100–230 cm | Audio + visual alert; CV takes over |
| `STOP & EXTEND` | 20–100 cm | Issue stop command; extend coupler arm |
| `COUPLING` | 5–20 cm | Fine alignment from 6-DOF pose data |
| `CONTACT CONFIRMED` | ≤ 5 cm | Inductive sensors confirm lock |

**Computer Vision Pipeline:**
1. Camera calibrated via `cv2.calibrateCamera` (checkerboard, 30+ frames)
2. ChArUco detection: `detectMarkers` → `interpolateCornersCharuco`
3. 6-DOF pose: `cv2.solvePnP` (ITERATIVE) → rotation + translation vectors
4. Pose averaging buffer (median, N=5) for temporal stability
5. Reprojection error QA gate — bad frames rejected before fusion

**Custom 1D Kalman Filter:**

```python
class KalmanFilter1D:
    def __init__(self, Q=1.0, R=10.0):
        self.x = np.array([0., 0.])   # [position, velocity]
        self.P = np.eye(2) * 100
        self.Q, self.R = Q, R

    def predict(self, dt):
        F = np.array([[1, dt], [0, 1]])
        self.x = F @ self.x
        self.P = F @ self.P @ F.T + self.Q * np.eye(2)

    def update(self, z, H):
        y = z - H @ self.x
        S = float(H @ self.P @ H.T) + self.R
        K = self.P @ H.T / S
        self.x += K * y
        self.P = (np.eye(2) - np.outer(K, H)) @ self.P
```

---

### Results

| Metric | Value |
|--------|-------|
| Positional accuracy (preliminary) | **~3 cm** |
| Operating range | 50–230 cm |
| Target accuracy (final) | 0.7 cm |
| Frame rate on RPi 4B | 15–30 FPS |
| End-to-end latency | < 100 ms |

---

### Future Work

- Global shutter camera + IR retroreflective markers for all-lighting robustness
- FMCW 77 GHz radar for absolute distance measurement
- LQR / neural-network closed-loop controller for fully autonomous approach
- CAN bus integration for direct coupler actuation
- UK Railway safety compliance (RSSB standards)
