# Requirements Document

## Introduction

This feature adds a `/cv/` page to the Jekyll site at slava-yr.github.io. The page renders a structured, web-optimized Curriculum Vitae for Salvador Yabar Reaño, covering Education, Research Interests, Publications, Skills, Awards & Competitions, and Languages. The page uses the site's existing `single` layout with `author_profile: true`, links to the existing PDF resume for download, cross-references existing `_publications/` collection entries rather than duplicating content, and is reachable via the site's main navigation. The existing PDF at `files/SalvadorYabar_OnePageResume.pdf` is not modified.

## Glossary

- **CV Page**: The Markdown file `_pages/cv.md` that Jekyll builds into the `/cv/` URL.
- **Site Layout**: The Jekyll `single` layout defined in the theme and referenced via front matter.
- **Navigation File**: The YAML file `_data/navigation.yml` that controls site header links.
- **Publications Collection**: The Jekyll collection stored in `_publications/`, each entry having a `permalink`, `title`, `venue`, `date`, and `category` front matter field.
- **PDF Resume**: The existing file `files/SalvadorYabar_OnePageResume.pdf`; must not be modified.
- **Download Button**: An HTML anchor styled with the theme's `btn btn--primary` class that links to the PDF Resume.
- **Author Profile Sidebar**: The sidebar rendered when `author_profile: true` is set in page front matter.

## Requirements

### Requirement 1: CV Page File

**User Story:** As a site visitor, I want to navigate to `/cv/` and see a structured CV, so that I can review Salvador's academic and professional background in a readable web format.

#### Acceptance Criteria

1. THE CV Page SHALL be located at `_pages/cv.md` and include front matter with `permalink: /cv/`, `title: "CV"`, `layout: single`, and `author_profile: true`.
2. THE CV Page SHALL render under the site's existing `single` layout without requiring any changes to layout templates.
3. THE CV Page SHALL include the following top-level sections in order: a download prompt, Education, Research Interests, Publications, Skills, Awards & Competitions, and Languages.

### Requirement 2: Download Button

**User Story:** As a site visitor, I want a clearly visible link to download the PDF resume from the CV page, so that I can obtain a print-ready version without searching elsewhere.

#### Acceptance Criteria

1. THE CV Page SHALL display a Download Button at the top of the page body, before any CV section content.
2. THE Download Button SHALL link to `/files/SalvadorYabar_OnePageResume.pdf` using an HTML anchor with class `btn btn--primary`.
3. THE PDF Resume SHALL remain at its existing path and SHALL NOT be renamed, moved, or modified.

### Requirement 3: Education Section

**User Story:** As a site visitor reviewing academic credentials, I want to see Salvador's degree, institution, location, and year, so that I can assess his academic background.

#### Acceptance Criteria

1. THE CV Page SHALL include an Education section containing the degree name (B.Sc. Electronics Engineering), institution (Pontificia Universidad Católica del Perú — PUCP), location (Lima, Peru), and graduation year.
2. THE CV Page SHALL include a short thesis title or relevant coursework note within the Education section.

### Requirement 4: Research Interests Section

**User Story:** As a researcher or recruiter, I want to read a concise statement of Salvador's research interests, so that I can quickly determine topical alignment.

#### Acceptance Criteria

1. THE CV Page SHALL include a Research Interests section listing Salvador's primary research topics: data-driven methods for photovoltaic systems, solar irradiance forecasting, embedded AI on low-cost microcontrollers, and machine learning for renewable energy systems.

### Requirement 5: Publications Section

**User Story:** As an academic reviewer, I want to see all publications listed chronologically with links to their detail pages, so that I can access full abstracts and downloads without content being duplicated on the CV page.

#### Acceptance Criteria

1. THE CV Page SHALL include a Publications section listing all entries from the `_publications/` collection.
2. WHEN listing a publication, THE CV Page SHALL display the publication title as a hyperlink pointing to the entry's `permalink` defined in that entry's front matter.
3. WHEN listing a publication, THE CV Page SHALL display the `venue` and `date` fields from the entry's front matter alongside the title.
4. THE CV Page SHALL list publications in chronological order by `date` (earliest first).
5. THE CV Page SHALL NOT duplicate the abstract, keywords, or download links already present on each publication's own detail page.

### Requirement 6: Skills Section

**User Story:** As a recruiter or potential collaborator, I want to see Salvador's technical skills organized by category, so that I can quickly match his expertise to a role or project.

#### Acceptance Criteria

1. THE CV Page SHALL include a Skills section.
2. THE Skills section SHALL organize skills into logical categories covering at minimum: programming languages and scientific computing (Python, MATLAB/Simulink), machine learning frameworks (TensorFlow/TinyML, Scikit-learn, XGBoost, Pandas/NumPy), and embedded systems (ESP32). Web and cloud technologies (Next.js/TypeScript, AWS) SHALL NOT appear in the Skills section.

### Requirement 7: Awards and Competitions Section

**User Story:** As a site visitor assessing Salvador's achievements, I want to see his competition awards with names and years, so that I can understand his track record.

#### Acceptance Criteria

1. THE CV Page SHALL include an Awards & Competitions section listing at minimum the following entries: 2nd place at SALA 2026 Hackathon (GalapagOS project), Top 30 at the Kiro Hackathon (Rimay project), and 2nd place at Reto de Innovación Ambiental 2025.
2. WHEN listing an award, THE CV Page SHALL include the award rank or title, the competition name, and the year.

### Requirement 8: Languages Section

**User Story:** As an international recruiter, I want to see Salvador's language proficiencies and certifications, so that I can assess communication fit for a position.

#### Acceptance Criteria

1. THE CV Page SHALL include a Languages section listing Spanish (Native) and English (Professional).
2. THE Languages section SHALL include a TOEFL certification entry with the following sub-scores: Reading 6.0, Listening 6.0, Writing 5.5, Speaking 5.0; test date October 10, 2026.

### Requirement 9: Navigation Integration

**User Story:** As a site visitor, I want to find the CV page from the site's main navigation, so that I can reach it without knowing the URL in advance.

#### Acceptance Criteria

1. THE Navigation File SHALL include a `main` navigation entry with `title: "CV"` and `url: /cv/`.
2. WHEN the Navigation File is updated, THE existing PDF-only navigation entry for CV SHALL be replaced by the entry pointing to `/cv/` so that only one CV link appears in the header.

### Requirement 11: Toggleable Sections

**User Story:** As a site visitor, I want to expand and collapse individual CV sections, so that I can focus on the parts most relevant to me without scrolling through the full page.

#### Acceptance Criteria

1. EACH CV section (Education, Research Interests, Publications, Skills, Awards & Competitions, Languages) SHALL be wrapped in an HTML `<details>` element with a `<summary>` tag containing the section heading text.
2. EACH section SHALL be open (expanded) by default using the `open` attribute on the `<details>` element.
3. THE toggle behaviour SHALL use native HTML `<details>`/`<summary>` with no custom JavaScript required.
4. THE visual style of the `<summary>` tag SHALL be consistent with the site's existing heading style; a CSS rule in the page or an inline style SHALL make `<summary>` render at the appropriate heading weight.

### Requirement 10: Visual and Tonal Consistency

**User Story:** As a site visitor, I want the CV page to look and read consistently with the rest of the site, so that the experience feels cohesive.

#### Acceptance Criteria

1. THE CV Page SHALL use Markdown heading levels (`##` for section headings) consistent with other `_pages/` files on the site.
2. THE CV Page SHALL NOT include emoji in any section headings or body text.
3. THE CV Page SHALL use plain prose and lists; decorative or novelty formatting SHALL NOT appear on the page.
