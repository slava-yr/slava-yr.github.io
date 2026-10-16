# Design Document

## Overview

The `/cv/` page is a new static page added to the existing Jekyll site at slava-yr.github.io. It uses the site's `single` layout with `author_profile: true`, requires no changes to `_layouts`, `_includes`, or `_config.yml`, and introduces no new dependencies. The page renders a structured CV with a download button, cross-references the existing `_publications/` collection via Liquid templating, and replaces the existing PDF-only link in `_data/navigation.yml`.

## Architecture

The implementation touches exactly two files plus one new file:

1. **`_pages/cv.md`** (new) — the CV page itself, a Markdown file with front matter and a Liquid loop over `site.publications`.
2. **`_data/navigation.yml`** (modified) — uncomments `url: /cv/` and removes (or comments out) the PDF URL so exactly one CV nav entry exists.
3. **`.kiro/specs/cv-page/.config.kiro`** (new) — workflow config file.

No layouts, includes, stylesheets, JavaScript, or Jekyll configuration files are modified.

## Components and Interfaces

### CV Page (`_pages/cv.md`)

The page front matter declares:

```yaml
---
permalink: /cv/
title: "CV"
layout: single
author_profile: true
---
```

The page body is structured as follows (in order):

1. **Download prompt** — a short sentence followed by an HTML anchor with `class="btn btn--primary"` pointing to `/files/SalvadorYabar_OnePageResume.pdf`. This appears before any section.
2. **Education** — wrapped in `<details open><summary>Education</summary>` … `</details>`.
3. **Research Interests** — same `<details>` wrapper.
4. **Publications** — `<details>` wrapper containing the Liquid loop (see below).
5. **Skills** — `<details>` wrapper with categorized bullet lists.
6. **Awards & Competitions** — `<details>` wrapper.
7. **Languages** — `<details>` wrapper.

Each section uses a `<details open>` element so all sections are expanded by default. The `<summary>` tag acts as the section heading. A short `<style>` block at the top of the page body styles `details summary` to match the site's `h2` weight (font-size and font-weight), ensuring visual consistency without modifying any theme files.

All section text content inside `<details>` is plain Markdown/HTML. No emoji appear anywhere. No decorative formatting is used.

### Publications Liquid Loop

The publications section uses a Liquid `assign` + `sort` + `for` loop:

```liquid
{% assign sorted_pubs = site.publications | sort: "date" %}
{% for pub in sorted_pubs %}
- [{{ pub.title }}]({{ pub.permalink }}) — {{ pub.venue }}, {{ pub.date | date: "%Y" }}
{% endfor %}
```

This renders each publication as a list item containing:
- The **title** as a hyperlink whose `href` is the entry's `permalink`.
- The **venue** string from front matter.
- The **year** extracted from the `date` front matter field.

No abstract, excerpt, keywords, or `paperurl` fields are output.

### Navigation Update (`_data/navigation.yml`)

The existing entry:

```yaml
main:
  - title: "CV"
    #url: /cv/
    url: /files/SalvadorYabar_OnePageResume.pdf
```

is replaced with:

```yaml
main:
  - title: "CV"
    url: /cv/
```

This ensures exactly one CV entry appears in the site header, pointing to the new page rather than directly to the PDF.

### External Interfaces

The CV page consumes:
- `site.publications` — Jekyll collection; read via Liquid.
- `/files/SalvadorYabar_OnePageResume.pdf` — existing file; referenced but not modified.
- Theme CSS classes `btn` and `btn--primary` — existing; not redefined.

The CV page exposes:
- URL `/cv/` — linked from navigation and any internal cross-references.

## Data Models

The `_publications/` collection entries are consumed read-only. The relevant front matter fields are:

| Field | Type | Usage on CV page |
|---|---|---|
| `title` | string | Link text |
| `permalink` | string | Link `href` |
| `venue` | string | Displayed after the link |
| `date` | date | Sorted on; year extracted for display |
| `excerpt`, `paperurl`, `tags` | — | Not accessed by the CV template |

## Error Handling

Jekyll processes the `sort: "date"` filter at build time. If a publication entry is missing the `date` field, Jekyll will silently place it at the beginning of the sorted list (nil sorts first). This is acceptable; no runtime error handling is required since Jekyll is a static site generator.

If the `_publications/` collection is empty, the Liquid loop outputs nothing under the Publications heading, which degrades gracefully.

## Testing Strategy

Because this feature produces a static Jekyll page with a Liquid template loop, most acceptance criteria are verified by inspecting the generated file content rather than running application code. The dual approach is:

**Example-based / smoke tests** cover static content requirements: the presence and ordering of section headings, download button placement and attributes, hard-coded CV content (Education, Research Interests, Skills, Awards, Languages), navigation.yml having exactly one CV entry, and the absence of emoji or decorative formatting. These are single-execution checks against the file content.

**Property-based tests** cover the Liquid template's behaviour over the `_publications/` collection — specifically that every entry appears as a correctly structured list item and that the display order matches ascending date order. Because behaviour varies with the set of publications (different titles, permalinks, venues, dates), property-based testing is appropriate and can run entirely in-memory without invoking Jekyll.

## Correctness Properties

*A property is a characteristic or behavior that should hold true across all valid executions of a system — essentially, a formal statement about what the system should do. Properties serve as the bridge between human-readable specifications and machine-verifiable correctness guarantees.*

### Property 1: Publication list item completeness

*For any* publication entry in the `_publications/` collection, the rendered Publications section of the CV page must include a list item that contains the entry's `title` as the anchor text, the entry's `permalink` as the anchor `href`, the entry's `venue` value, and a year extracted from the entry's `date` field — and must not include the entry's `excerpt`, `paperurl`, or `tags` fields.

**Validates: Requirements 5.1, 5.2, 5.3, 5.5**

### Property 2: Publications rendered in ascending date order

*For any* set of publication entries with distinct `date` values, the order of publication titles as they appear in the rendered Publications section must correspond to the ascending sort order of their `date` values (earliest date listed first).

**Validates: Requirements 5.4**
