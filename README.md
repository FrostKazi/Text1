# Kazi Abdul Baset — Engineering Portfolio

Personal robotics & engineering portfolio built with [al-folio](https://github.com/alshedivat/al-folio) and hosted on GitHub Pages.

**Live site:** [frostkazi.github.io/Text1](https://frostkazi.github.io/Text1)

---

## Projects

| # | Project | Tech | Status |
|---|---------|------|--------|
| 1 | [Virtual Buffer](https://frostkazi.github.io/Text1/projects/1-virtual-buffer/) — Vision & radar sensor fusion for semi-autonomous train coupling | Python, OpenCV, Kalman Filter, mmWave Radar | MSc Dissertation |
| 2 | [LeaseMate](https://frostkazi.github.io/Text1/projects/2-leasemate/) — AI rental contract analyser | Python, Flask, LLM, Tailwind CSS | HackSussex 2026 Grand Prize |
| 3 | [SpotMicro](https://frostkazi.github.io/Text1/projects/3-spotmicro/) — 3D-printed quadruped robot | ESP32-S3, Fusion 360, Servo Control | FYP Complete |
| 4 | [Smart Parking](https://frostkazi.github.io/Text1/projects/4-smart-parking/) — ANPR + automated billing | Python, OpenCV, MySQL, Streamlit | Complete |
| 5 | [Space to Storage](https://frostkazi.github.io/Text1/projects/5-space-to-storage/) — Agricultural satellite platform | Next.js, FastAPI | Complete |
| 6 | [RC AeroBoat](https://frostkazi.github.io/Text1/projects/6-rc-aeroboat/) — Water pollution combat boat | Arduino, Brushless Motors | Robothon 2022 Runner-Up |
| 7 | [Robotic Arm](https://frostkazi.github.io/Text1/projects/7-robotic-arm/) — Vision-guided manipulation | Fusion 360, Arduino, ROS, OpenCV | In Progress |
| 8 | [RI One RPi4 Console](https://frostkazi.github.io/Text1/projects/8-rpi4-console/) — Custom 3D-printed retro console | Raspberry Pi 4, Fusion 360 | Published on Printables |

---

## Adding Your Project Images

Upload images to `assets/img/projects/` with filenames matching the `img:` field in each `_projects/*.md` file. Supported: `.jpg`, `.png`, `.gif` (GIFs autoplay in the browser for hardware demos).

```
assets/img/projects/virtual-buffer.jpg
assets/img/projects/leasemate.jpg
assets/img/projects/spotmicro.jpg
...etc
```

## Updating Your CV

Replace `assets/pdf/resume.pdf` with your latest CV — the PDF viewer on `/cv/` will pick it up automatically on the next build.

## Deployment

Site is auto-deployed via GitHub Actions (`.github/workflows/deploy.yml`) whenever you push to `main`. Build takes ~3–5 minutes.

Check build status: `github.com/FrostKazi/Text1 → Actions tab`

## Adding a New Project

1. Duplicate any file in `_projects/`
2. Update the front matter (title, description, img, importance, tags, github)
3. Write the body content
4. Upload a thumbnail to `assets/img/projects/`
5. Commit and push — site rebuilds automatically

---

Built with [al-folio](https://github.com/alshedivat/al-folio) • [Jekyll](https://jekyllrb.com/) • [GitHub Pages](https://pages.github.com/)
