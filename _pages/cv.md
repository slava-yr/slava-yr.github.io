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

<p><strong>B.Sc. Electronics Engineering</strong><br>
Pontificia Universidad Católica del Perú (PUCP) — Lima, Peru<br>
Graduated: 2026</p>

<p>Thesis: <em>Data-Driven Maximum Power Point Tracking for Photovoltaic Systems Using Machine Learning and Embedded Deployment</em></p>

<p>Relevant coursework: Digital Signal Processing, Control Systems, Embedded Systems, Machine Learning, Power Electronics.</p>

</details>

<details open>
<summary>Research Interests</summary>

<ul>
  <li>Data-driven methods for photovoltaic systems (MPPT, feature selection, forecasting)</li>
  <li>Solar irradiance forecasting under variable climate conditions</li>
  <li>Embedded AI and TinyML deployment on low-cost microcontrollers</li>
  <li>Machine learning for renewable energy systems</li>
</ul>

</details>

<details open>
<summary>Publications</summary>

<ul>
{% assign sorted_pubs = site.publications | sort: "date" | reverse %}
{% for pub in sorted_pubs %}
  <li><a href="{{ pub.url }}">{{ pub.title }}</a> — {{ pub.venue }}, {{ pub.date | date: "%Y" }}</li>
{% endfor %}
</ul>

</details>

<details open>
<summary>Skills</summary>

<p><strong>Programming &amp; Scientific Computing</strong></p>
<ul>
  <li>Python (NumPy, Pandas, Scikit-learn, XGBoost, Matplotlib)</li>
  <li>MATLAB / Simulink</li>
</ul>

<p><strong>Machine Learning &amp; AI</strong></p>
<ul>
  <li>TensorFlow / Keras</li>
  <li>TinyML (model quantization, embedded inference)</li>
  <li>Scikit-learn, XGBoost</li>
</ul>

<p><strong>Embedded Systems</strong></p>
<ul>
  <li>ESP32 (Arduino / ESP-IDF)</li>
  <li>Hardware-in-the-Loop (HIL) testing</li>
  <li>C / C++ for microcontrollers</li>
</ul>

</details>

<details open>
<summary>Awards &amp; Competitions</summary>

<ul>
  <li><strong>2nd place</strong> — SALA 2026 Hackathon, GalapagOS project (2026)</li>
  <li><strong>Top 30</strong> — Kiro Hackathon, Rimay project (2025)</li>
  <li><strong>2nd place</strong> — Reto de Innovación Ambiental, CIDE-PUCP (2025)</li>
</ul>

</details>

<details open>
<summary>Languages</summary>

<ul>
  <li><strong>Spanish</strong> — Native</li>
  <li><strong>English</strong> — Professional working proficiency
    <ul>
      <li>TOEFL certification (October 10, 2026): Reading 6.0 · Listening 6.0 · Writing 5.5 · Speaking 5.0</li>
    </ul>
  </li>
</ul>

</details>
