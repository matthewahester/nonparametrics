# CLAUDE.md — nonparametrics (public Quarto site)

_Notes for Claude Code or any AI assistant working in this repo._

## What this repo is

The **public-facing Quarto course-materials site** for **Resampling, Nonparametric & Robust Methods**
assembled by Matt Hester. It is a sibling of the main site
[matthewhester.com](https://matthewhester.com) and is intended to live at
`/nonparametrics/` under that domain, alongside the other course sites.

It holds **assembled course material** — the course's own synthesized
notes, hands-on R labs, and curated resources.

## What this repo is not

- It is **not** the private course build. That lives in a separate,
  Drive-synced teaching workspace and is not part of this repository.
- It is **not** a claim that the course is currently being taught. This
  is durable, public course material; honest wording is "assembled
  course materials," not "a course I am teaching now."
- It is **not** the LMS. **Blackboard remains authoritative** for grades,
  due dates, submissions, rosters, and anything operational.

## Do not add to this repo

- Answer keys or solutions (any form: PDF, TeX, Markdown, `_key.*`).
- Assessment items, specs, manifests, scenarios, rubrics, point values.
- Anything from the private course build: `_state/`,
  `assessment_shadow/`, `source_text/`, `run_reports/`, `accessibility/`,
  `export/`.
- Real or student data, FERPA-adjacent material, gradebook exports,
  rosters, `.rds`/`.RData` artifacts.

When unsure, default to **don't publish** and ask.

## Provenance

Assembled (2026-06) from a course-material build. Only the public surface
was promoted: `index.qmd`, `syllabus.qmd`, `schedule.qmd`, `notes/`,
`labs/`, `resources/`, `styles.css`, and `_quarto.yml`. Every private
directory listed above was deliberately left behind.

## Rendering

- R code is written as **static, non-executed** ```r fences, so
  `quarto render` builds the whole site **without R** (deterministic).
  Output goes to `_site/` (gitignored).
- The combined public site is assembled and deployed by the hub repo
  (`matthewhester-site`); this repo has no CI of its own.

## Images

- `assets/hero.png` — full course-identity banner (carries the title);
  referenced on `index.qmd` with `.course-hero-img` and alt text.
- `assets/icon.png` — square crystal mark with transparent background
  (a red-orange vanadinite square mark); wired as the navbar `logo`.

## Hard rules for Claude in this repo

- **Commit only when explicitly instructed.** Never push without explicit
  instruction.
- **Do not reach back into the private course build** unless explicitly
  instructed.
