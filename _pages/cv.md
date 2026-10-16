---
permalink: /cv/
title: "CV"
layout: single
author_profile: true
---

<style>
details { margin-bottom: 1.5em; }
details summary {
  font-size: 1.3em;
  font-weight: 700;
  cursor: pointer;
  list-style: none;
  padding: 0.2em 0;
  border-bottom: 1px solid #ccc;
  margin-bottom: 0.75em;
}
details summary::-webkit-details-marker { display: none; }
details summary::before {
  content: "▸ ";
  font-size: 0.85em;
  color: #888;
}
details[open] summary::before { content: "▾ "; }
</style>

Download a print-ready version of this CV:

<a href="/files/SalvadorYabar_OnePageResume.pdf" class="btn btn--primary">Download PDF Resume</a>

---

<details open>
<summary>Education</summary>

**B.Sc. Electronics Engineering**  
Pontificia Universidad Católica del Perú (PUCP) — Lima, Peru  
Graduated: 2026

Thesis: *Data-Driven Maximum Power Point Tracking for Photovoltaic Systems Using Machine Learning and Embedded Deployment*

Relevant coursework: Digital Signal Processing, Control Systems, Embedded Systems, Machine Learning, Power Electronics.

</details>

<details open>
<summary>Research Interests</summary>

- Data-driven methods for photovoltaic systems (MPPT, feature selection, forecasting)
- Solar irradiance forecasting under variable climate conditions
- Embedded AI and TinyML deployment on low-cost microcontrollers
- Machine learning for renewable energy systems

</details>

<details open>
<summary>Publications</summary>

{% assign sorted_pubs = site.publications | sort: "date" %}
{% for pub in sorted_pubs %}
- [{{ pub.title }}]({{ pub.permalink }}) — {{ pub.venue }}, {{ pub.date | date: "%Y" }}
{% endfor %}

</details>

<details open>
<summary>Skills</summary>

**Programming & Scientific Computing**
- Python (NumPy, Pandas, Scikit-learn, XGBoost, Matplotlib)
- MATLAB / Simulink

**Machine Learning & AI**
- TensorFlow / Keras
- TinyML (model quantization, embedded inference)
- Scikit-learn, XGBoost

**Embedded Systems**
- ESP32 (Arduino / ESP-IDF)
- Hardware-in-the-Loop (HIL) testing
- C / C++ for microcontrollers

</details>

<details open>
<summary>Awards & Competitions</summary>

- **2nd place** — SALA 2026 Hackathon, GalapagOS project (2026)
- **Top 30** — Kiro Hackathon, Rimay project (2025)
- **2nd place** — Reto de Innovación Ambiental, CIDE-PUCP (2025)

</details>

<details open>
<summary>Languages</summary>

- **Spanish** — Native
- **English** — Professional working proficiency
  - TOEFL certification (October 10, 2026): Reading 6.0 · Listening 6.0 · Writing 5.5 · Speaking 5.0

</details>
