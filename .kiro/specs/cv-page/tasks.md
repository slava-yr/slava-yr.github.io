# Implementation Plan: CV Page

## Overview

Add a `/cv/` page to the Jekyll site by creating `_pages/cv.md` with the correct front matter, download button, and all CV sections, updating `_data/navigation.yml` to point to `/cv/`, and writing tests that verify section headings, download button attributes, navigation entry, and publication list completeness and ordering.

## Tasks

- [x] 1. Update navigation to point to the new CV page
  - [x] 1.1 Replace the PDF-only CV entry in `_data/navigation.yml` with `url: /cv/`
    - Remove the `#url: /cv/` comment line and the `url: /files/SalvadorYabar_OnePageResume.pdf` line; add `url: /cv/` so exactly one CV entry exists
    - _Requirements: 9.1, 9.2_

- [ ] 2. Create the CV page
  - [ ] 2.1 Create `_pages/cv.md` with correct front matter, download button, and toggleable section structure
    - Add front matter: `permalink: /cv/`, `title: "CV"`, `layout: single`, `author_profile: true`
    - Add a `<style>` block styling `details summary` to render at `h2` weight (no theme files modified)
    - Add a short download prompt followed by `<a href="/files/SalvadorYabar_OnePageResume.pdf" class="btn btn--primary">Download PDF Resume</a>` before any section
    - Wrap every section in `<details open><summary>Section Name</summary>` … `</details>`
    - _Requirements: 1.1, 1.2, 1.3, 2.1, 2.2, 2.3, 11.1, 11.2, 11.3, 11.4_

  - [ ] 2.2 Add Education and Research Interests sections to `_pages/cv.md`
    - Write `## Education` with degree (B.Sc. Electronics Engineering), institution (Pontificia Universidad Católica del Perú — PUCP), location (Lima, Peru), graduation year, and a short thesis/coursework note
    - Write `## Research Interests` as a bullet list covering: data-driven methods for photovoltaic systems, solar irradiance forecasting, embedded AI on low-cost microcontrollers, machine learning for renewable energy systems
    - Use `##` headings; no emoji; plain prose and lists only
    - _Requirements: 3.1, 3.2, 4.1, 10.1, 10.2, 10.3_

  - [ ] 2.3 Add Publications section with Liquid loop to `_pages/cv.md`
    - Write `## Publications` followed by a Liquid snippet that assigns `sorted_pubs = site.publications | sort: "date"`, loops over it, and renders each entry as `- [{{ pub.title }}]({{ pub.permalink }}) — {{ pub.venue }}, {{ pub.date | date: "%Y" }}`
    - No abstract, excerpt, paperurl, or tags fields are output
    - _Requirements: 5.1, 5.2, 5.3, 5.4, 5.5_

  - [ ] 2.4 Add Skills, Awards & Competitions, and Languages sections to `_pages/cv.md`
    - Write `## Skills` with categorised bullet lists covering: Python / MATLAB/Simulink, TensorFlow/TinyML / Scikit-learn / XGBoost / Pandas/NumPy, ESP32 — Next.js/TypeScript and AWS SHALL NOT appear
    - Write `## Awards & Competitions` listing: 2nd place — SALA 2026 Hackathon (GalapagOS), 2026; Top 30 — Kiro Hackathon (Rimay), 2025; 2nd place — Reto de Innovación Ambiental 2025, 2025 — each with rank/title, competition name, and year
    - Write `## Languages` listing Spanish (Native) and English (Professional), with a TOEFL certification entry showing sub-scores (Reading 6.0, Listening 6.0, Writing 5.5, Speaking 5.0) and test date (October 10, 2026)
    - _Requirements: 6.1, 6.2, 7.1, 7.2, 8.1, 10.1, 10.2, 10.3_

- [ ] 3. Checkpoint — Verify the page builds
  - Ensure all tests pass, ask the user if questions arise.

- [ ] 4. Write tests
  - [ ] 4.1 Write smoke tests for static page content
    - Read `_pages/cv.md` as text and assert: front matter contains `permalink: /cv/`, `layout: single`, `author_profile: true`; the download anchor `href` is `/files/SalvadorYabar_OnePageResume.pdf` and its `class` includes `btn btn--primary`; the anchor appears before the first `##` heading; all seven required section headings are present in order (`## Education`, `## Research Interests`, `## Publications`, `## Skills`, `## Awards & Competitions`, `## Languages`); no emoji character appears in any heading
    - Read `_data/navigation.yml` and assert: exactly one entry has `title: "CV"`; its `url` is `/cv/`; no entry has `url` containing `SalvadorYabar_OnePageResume.pdf`
    - _Requirements: 1.1, 1.2, 1.3, 2.1, 2.2, 2.3, 9.1, 9.2, 10.1, 10.2_

  - [ ]* 4.2 Write property test for publication list item completeness (Property 1)
    - **Property 1: Publication list item completeness**
    - **Validates: Requirements 5.1, 5.2, 5.3, 5.5**
    - Generate arbitrary sets of publication objects (title, permalink, venue, date); render the Liquid template loop logic in Python; for each publication assert the rendered output contains an anchor whose text is `title`, whose href is `permalink`, and whose surrounding text includes `venue` and the four-digit year extracted from `date`; assert `excerpt`, `paperurl`, and `tags` do not appear in any list item

  - [ ]* 4.3 Write property test for publications ascending date order (Property 2)
    - **Property 2: Publications rendered in ascending date order**
    - **Validates: Requirements 5.4**
    - Generate arbitrary lists of publication objects with distinct `date` values; sort by date ascending; render the list in the same order; assert the sequence of titles in the output matches the ascending-date ordering for all generated inputs

- [ ] 5. Final checkpoint — Ensure all tests pass
  - Ensure all tests pass, ask the user if questions arise.

## Notes

- Tasks marked with `*` are optional and can be skipped for faster MVP
- Each task references specific requirements for traceability
- Checkpoints ensure incremental validation
- Property tests validate universal correctness properties defined in the design document
- Unit tests validate specific examples and edge cases

## Task Dependency Graph

```json
{
  "waves": [
    { "id": 0, "tasks": ["1.1"] },
    { "id": 1, "tasks": ["2.1"] },
    { "id": 2, "tasks": ["2.2", "2.3", "2.4"] },
    { "id": 3, "tasks": ["4.1"] },
    { "id": 4, "tasks": ["4.2", "4.3"] }
  ]
}
```
