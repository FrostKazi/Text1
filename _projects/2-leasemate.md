---
layout: page
title: "LeaseMate — AI Rental Contract Analyser"
description: "HackSussex 2026 Overall Grand Prize Winner. UK tenancy agreement auditor: upload PDF/Word contract → LLM analysis grounded in curated UK housing law YAML → severity-ranked clause warnings. Built in 24 hours."
img: assets/img/projects/leasemate.jpg
importance: 2
category: software
tags: [Python, Flask, HTML5, Tailwind CSS, PyMuPDF, python-docx, LLM, YAML, JavaScript]
github: https://github.com/FrostKazi/LeaseMate
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

LeaseMate is a UK rental contract AI analyser built for student renters: upload your PDF or Word tenancy agreement → LeaseMate extracts the text, runs it through an LLM grounded against a curated YAML knowledge base of UK housing law (including the **Renters' Rights Act 2025**), and outputs severity-ranked clause warnings as interactive action cards.

**Won the Overall Grand Prize at HackSussex 2026** across all competition tracks, beating dedicated software, hardware, and social-good tracks. Built by a team of 4 (3 law students + 1 engineer) in 24 hours.

---

### Components

**Frontend:** HTML5 + Vanilla JS + Tailwind CSS
- Drag-and-drop file upload (PDF and .docx)
- Dynamic severity-ranked action cards rendered from structured JSON

**Backend:** Python + Flask
- PyMuPDF for robust PDF text extraction
- python-docx for Word document extraction
- LLM integration with custom grounding pipeline

**Knowledge Base:** YAML-structured UK housing law
- Renters' Rights Act 2025 clauses and protections
- Severity-mapped unfair clause patterns

---

### Architecture → LLM Grounding Pipeline

The core engineering challenge: **preventing AI hallucination in a legal context.**

```
Upload (PDF / Word)
       ↓
Text Extraction (PyMuPDF / python-docx)
       ↓
Clause Segmentation
       ↓
LLM Prompt (clause + relevant YAML law sections injected)
       ↓
Forced structured JSON output schema
       ↓
Severity-ranked action cards  [ HIGH | MEDIUM | LOW ]
```

By injecting only relevant UK statute text from the curated YAML into each prompt, the model is anchored to verified law — it cannot invent clauses. Constrained JSON output ensures the frontend never receives malformed responses.

---

### Results

- **HackSussex 2026 Overall Grand Prize** — won across all competition tracks
- 100% detection rate on deliberately planted illegal clauses in test contracts
- Tested on real student tenancy agreements from Sussex Student Union
- **Next:** Partner with Student Unions for campus-wide deployment
