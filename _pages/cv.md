---
permalink: /cv/
title: "CV"
layout: single
author_profile: true
---

<style>
.cv-section {
  margin-bottom: 2em;
}
.cv-section h2 {
  font-size: 1.1em;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #888;
  border-bottom: 1px solid #ddd;
  padding-bottom: 0.3em;
  margin-bottom: 1em;
}
.cv-entry {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  flex-wrap: wrap;
  gap: 0.2em;
  margin-bottom: 0.15em;
}
.cv-entry-left { flex: 1; min-width: 0; }
.cv-entry-date {
  font-size: 0.85em;
  color: #888;
  white-space: nowrap;
  margin-left: 1em;
}
.cv-role { font-weight: 700; }
.cv-org { font-style: italic; color: #555; }
.cv-bullets {
  margin: 0.3em 0 0.9em 0;
  padding-left: 1.4em;
  font-size: 0.93em;
  color: #444;
}
.cv-bullets li { margin-bottom: 0.15em; }
.cv-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4em;
  margin-top: 0.5em;
}
.cv-tag {
  background: #f0f0f0;
  border-radius: 3px;
  padding: 0.15em 0.6em;
  font-size: 0.82em;
  color: #444;
}
.cv-award-row {
  display: flex;
  justify-content: space-between;
  font-size: 0.93em;
  margin-bottom: 0.3em;
  flex-wrap: wrap;
}
.cv-award-row span { color: #888; font-size: 0.9em; }
</style>

<a href="/files/SalvadorYabar_OnePageResume.pdf" class="btn btn--primary">Download PDF Resume</a>

---

<div class="cv-section">
<h2>Education</h2>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">B.Sc. Electronics Engineering</span> (Top 5%) &nbsp;·&nbsp; <span class="cv-org">Pontificia Universidad Católica del Perú (PUCP)</span>
  </div>
  <span class="cv-entry-date">Mar 2020 – Dec 2025</span>
</div>
<ul class="cv-bullets">
  <li>Thesis: <em>Neural Network-Based MPPT Optimization Algorithm for Photovoltaic Generation Systems</em></li>
</ul>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">Academic Exchange</span> — DARI Mobility Scholar &nbsp;·&nbsp; <span class="cv-org">University of Calgary</span>
  </div>
  <span class="cv-entry-date">Aug – Dec 2023</span>
</div>
<ul class="cv-bullets">
  <li>Coursework: Applied AI, Photovoltaic Systems Engineering, Embedded Systems Interfacing, Biomedical Design</li>
</ul>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">IB Diploma Programme</span> &nbsp;·&nbsp; <span class="cv-org">Bachillerato Internacional</span>
  </div>
  <span class="cv-entry-date">2018 – 2019</span>
</div>
</div>

---

<div class="cv-section">
<h2>Publications</h2>

<ul class="cv-bullets">
{% assign sorted_pubs = site.publications | sort: "date" | reverse %}
{% for pub in sorted_pubs %}
  <li><a href="{{ pub.url }}">{{ pub.title }}</a> — <em>{{ pub.venue }}</em>, {{ pub.date | date: "%Y" }}</li>
{% endfor %}
</ul>
</div>

---

<div class="cv-section">
<h2>Research &amp; Venture Experience</h2>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">Team Lead &amp; Primary Researcher</span> &nbsp;·&nbsp; <span class="cv-org">SALA '26 Hackathon — GalapagOS Project</span>
  </div>
  <span class="cv-entry-date">Mar – Jul 2026</span>
</div>
<ul class="cv-bullets">
  <li>Led team to 2nd place with an AI solar forecasting tool achieving 40% improvement over benchmark.</li>
  <li>Formalized forecasting architecture into a paper submitted to WAIMLAP.</li>
</ul>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">Data Analyst &amp; Researcher</span> &nbsp;·&nbsp; <span class="cv-org">MatEr Research Group, PUCP</span>
  </div>
  <span class="cv-entry-date">Dec 2025 – Jun 2026</span>
</div>
<ul class="cv-bullets">
  <li>Led cleaning, structuring, and validation of photovoltaic time-series datasets for AI model training.</li>
</ul>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">Co-Founder &amp; Hardware Lead</span> &nbsp;·&nbsp; <span class="cv-org">AgroScan – AgTech Startup</span>
  </div>
  <span class="cv-entry-date">May 2025 – Mar 2026</span>
</div>
<ul class="cv-bullets">
  <li>Built an autonomous agricultural robot for crop disease detection; advanced to final stage of ProInnovaTe funding.</li>
</ul>
</div>

---

<div class="cv-section">
<h2>Professional Experience</h2>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">Consultant</span> &nbsp;·&nbsp; <span class="cv-org">Management Solutions</span>
  </div>
  <span class="cv-entry-date">Aug 2026 – Present</span>
</div>

<div class="cv-entry" style="margin-top:0.6em">
  <div class="cv-entry-left">
    <span class="cv-role">IT Infrastructure Support Intern</span> &nbsp;·&nbsp; <span class="cv-org">PUCP</span>
  </div>
  <span class="cv-entry-date">Apr – Jul 2026</span>
</div>
<ul class="cv-bullets">
  <li>Managed diagnosis, maintenance, and continuity of laboratory equipment and network infrastructure.</li>
</ul>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">Digital Power Trainee</span> &nbsp;·&nbsp; <span class="cv-org">Huawei Digital Power</span>
  </div>
  <span class="cv-entry-date">Sep 2024 – Sep 2025</span>
</div>
<ul class="cv-bullets">
  <li>Operational diagnostics on Data Center Facilities (UPS, Precision Cooling); trained 10 strategic partners.</li>
</ul>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">Undergraduate Teaching Assistant — Physics</span> &nbsp;·&nbsp; <span class="cv-org">PUCP</span>
  </div>
  <span class="cv-entry-date">Mar – Jul 2024</span>
</div>
<ul class="cv-bullets">
  <li>Facilitated instruction and grading for first-semester Fundamentals of Physics.</li>
</ul>
</div>

---

<div class="cv-section">
<h2>Leadership &amp; Mentorship</h2>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">Research Mentor</span> &nbsp;·&nbsp; <span class="cv-org">Via Scientia</span>
  </div>
  <span class="cv-entry-date">Jan 2026 – Present</span>
</div>
<ul class="cv-bullets">
  <li>Mentoring high school and gap year students in scientific methodology and academic writing.</li>
</ul>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">Community Educational Volunteer</span> &nbsp;·&nbsp; <span class="cv-org">La Escuelita</span>
  </div>
  <span class="cv-entry-date">Jul 2026 – Present</span>
</div>
<ul class="cv-bullets">
  <li>Academic reinforcement for children in socio-economic vulnerability.</li>
</ul>

<div class="cv-entry">
  <div class="cv-entry-left">
    <span class="cv-role">Project Director</span> &nbsp;·&nbsp; <span class="cv-org">IEEE AESS PUCP</span>
  </div>
  <span class="cv-entry-date">Jan – Dec 2024</span>
</div>
<ul class="cv-bullets">
  <li>Led 25-member team to build an agricultural rover prototype for national competition.</li>
</ul>
</div>

---

<div class="cv-section">
<h2>Awards &amp; Recognition</h2>

<div class="cv-award-row"><div>🥈 <strong>2nd place</strong> — SALA 2026 Hackathon (GalapagOS)</div><span>2026</span></div>
<div class="cv-award-row"><div>🏆 <strong>Top 30</strong> — Kiro Hackathon (Rimay)</div><span>2025</span></div>
<div class="cv-award-row"><div>🥈 <strong>2nd place</strong> — Reto de Innovación Ambiental, CIDE-PUCP</div><span>2025</span></div>
<div class="cv-award-row"><div>🛰️ <strong>Finalist</strong> — National Small Satellite Competition</div><span>2024</span></div>
<div class="cv-award-row"><div>✈️ <strong>DARI Exchange Scholarship</strong> — University of Calgary</div><span>2023</span></div>
</div>

---

<div class="cv-section">
<h2>Skills &amp; Certifications</h2>

<div class="cv-tags">
  <span class="cv-tag">Python</span>
  <span class="cv-tag">TensorFlow / Keras</span>
  <span class="cv-tag">Scikit-learn</span>
  <span class="cv-tag">XGBoost</span>
  <span class="cv-tag">NumPy / Pandas</span>
  <span class="cv-tag">SQL</span>
  <span class="cv-tag">Power BI</span>
  <span class="cv-tag">C / C++</span>
  <span class="cv-tag">Embedded Systems</span>
  <span class="cv-tag">Edge AI / TinyML</span>
  <span class="cv-tag">MATLAB / Simulink</span>
  <span class="cv-tag">Git</span>
  <span class="cv-tag">LaTeX</span>
</div>

<p style="margin-top:1em; font-size:0.93em;">
  <strong>Certifications:</strong>
  Huawei Certified Specialist Expert (Data Center Facility) &nbsp;·&nbsp;
  Solar Energy and Electrical System Design &nbsp;·&nbsp;
  Python/Pandas Data Engineering — Duke University
</p>
</div>

---

<div class="cv-section">
<h2>Languages</h2>

<div class="cv-tags">
  <span class="cv-tag">Spanish — Native</span>
  <span class="cv-tag">English — Advanced</span>
  <span class="cv-tag">French — Basic</span>
</div>
</div>
