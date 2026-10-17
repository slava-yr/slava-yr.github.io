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

<p><strong>B.Sc. Electronics Engineering</strong> (Top 10%)<br>
Pontificia Universidad Católica del Perú (PUCP) — Lima, Peru<br>
Mar 2020 – Dec 2025</p>
<p>Thesis: <em>Neural Network-Based MPPT Optimization Algorithm for Photovoltaic Generation Systems</em></p>

<p><strong>Academic Exchange Program</strong> — DARI Mobility Scholar<br>
University of Calgary — Calgary, Canada<br>
Aug 2023 – Dec 2023</p>
<p>Coursework: Applied AI, Photovoltaic Systems Engineering, Embedded Systems Interfacing, Biomedical Design.</p>

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
<summary>Research &amp; Venture Experience</summary>

<p><strong>Team Lead &amp; Primary Researcher</strong><br>
Summit of AI in LatAm (SALA) &amp; GalapagOS Project — Quito, Ecuador / Remote<br>
Mar 2026 – Jul 2026</p>
<ul>
  <li>Led team to win 2nd place in the SALA Hackathon with an AI solar forecasting tool achieving 40% improvement over benchmark.</li>
  <li>Coordinated a 5-month research sprint to formalize the forecasting architecture into a paper submitted to WAIMLAP.</li>
</ul>

<p><strong>Data Analyst &amp; Research Lead</strong><br>
Material Science and Renewable Energy Research Group (MatEr) — Lima, Peru<br>
Dec 2025 – Jun 2026</p>
<ul>
  <li>Led cleaning, structuring, and validation of photovoltaic time-series datasets using Python for AI model training.</li>
</ul>

<p><strong>Co-Founder &amp; Hardware Lead</strong><br>
AgroScan – AgTech Startup — Lima, Peru<br>
May 2025 – Mar 2026</p>
<ul>
  <li>Co-founded an agtech venture building an autonomous agricultural robot for crop leaf disease detection.</li>
  <li>Graduated from the Equipu accelerator program; advanced to final pitch stage for ProInnovaTe funding.</li>
</ul>

</details>

<details open>
<summary>Professional Experience</summary>

<p><strong>IT Infrastructure Support Intern</strong><br>
Pontificia Universidad Católica del Perú (PUCP) — Lima, Peru<br>
Apr 2026 – Jul 2026</p>
<ul>
  <li>Managed diagnosis, maintenance, and operational continuity of laboratory equipment and network infrastructure.</li>
</ul>

<p><strong>Digital Power Trainee</strong><br>
Huawei Digital Power — Lima, Peru<br>
Sep 2024 – Sep 2025</p>
<ul>
  <li>Executed operational diagnostics on Data Center Facilities (UPS and Precision Cooling systems).</li>
  <li>Trained 10 strategic partners through official sessions, enabling status upgrades to authorized Gold channels.</li>
</ul>

</details>

<details open>
<summary>Leadership &amp; Mentorship</summary>

<p><strong>Research Mentor</strong><br>
Via Scientia — Lima, Peru<br>
Jan 2026 – Present</p>
<ul>
  <li>Mentoring high school and gap year students in scientific methodology and academic drafting.</li>
</ul>

<p><strong>Community Educational Volunteer</strong><br>
La Escuelita — Lima, Peru<br>
Jul 2026 – Present</p>
<ul>
  <li>Delivering academic reinforcement and educational support to children facing socio-economic poverty.</li>
</ul>

<p><strong>Project Director</strong><br>
IEEE Aerospace &amp; Electronic Systems Society PUCP — Lima, Peru<br>
Jan 2024 – Dec 2024</p>
<ul>
  <li>Led a 25-member interdisciplinary team to engineer an agricultural rover prototype for national competition.</li>
</ul>

</details>

<details open>
<summary>Skills &amp; Certifications</summary>

<p><strong>Technical Skills</strong></p>
<ul>
  <li>Python (NumPy, Pandas, TensorFlow, Scikit-learn, XGBoost)</li>
  <li>SQL, Power BI, Git, LaTeX</li>
  <li>C / C++, Embedded Systems, Edge AI / TinyML</li>
  <li>MATLAB / Simulink</li>
</ul>

<p><strong>Certifications</strong></p>
<ul>
  <li>Huawei Certified Specialist Expert — Data Center Facility</li>
  <li>Python/Pandas Data Engineering — Duke University</li>
</ul>

</details>

<details open>
<summary>Languages</summary>

<ul>
  <li><strong>Spanish</strong> — Native</li>
  <li><strong>English</strong> — Advanced (TOEFL, October 2026)</li>
  <li><strong>French</strong> — Basic</li>
  <li><strong>Japanese</strong> — Basic</li>
</ul>

</details>
