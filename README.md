# nonparametrics

Public-facing Quarto **course-materials site** for **Resampling, Nonparametric & Robust Methods**, assembled
by Matt Hester. Sibling to the main site
[matthewhester.com](https://matthewhester.com); intended to live at
`/nonparametrics/` under that domain.

This is **assembled course material** — synthesized lesson notes,
hands-on R labs, and curated references for assumption-light statistical reasoning. It is a durable
public resource site, **not** a record of a currently scheduled section,
and **not** an LMS.

## Status

Assembled from a course-material build (2026-06); a coherent **draft**,
not a finished release. Topic flow, notes, labs, and resources are in
place. Example datasets are synthetic and the numbers are provisional;
dates, weights, and final policies are not sealed and are authoritative
in the LMS (Blackboard) whenever the course runs.

## What this site holds

- **Notes** — the weekly instructional spine (15 weeks): empirical distributions, order statistics and ranks, permutation and randomization logic, bootstrap distributions and confidence intervals, rank-based one-sample/paired and two-sample methods, ordinal and categorical outcomes, robust summaries and outliers, robust-regression ideas, the honest comparison of parametric and nonparametric conclusions, and simulation studies of method behavior.
- **Labs** — four hands-on R labs (build a randomization test, bootstrap the median, robust regression versus least squares, and a method-comparison simulation).
- **Resources** — a method-chooser decision guide, a methods glossary, a resampling guide, and a robustness-and-outliers guide.

The notes are the course's **own synthesis**. R code is shown as
**static, non-executed** ```r fences (worked numbers are hand-authored
synthetic listings with seeds set); no R engine is invoked, so the site
renders deterministically.

## What does not go in this repo

Anything private to a graded offering: answer keys, assessment items,
rubrics, point values, due dates, student data, or any directory from the
private course build (`_state/`, `assessment_shadow/`, `source_text/`,
`run_reports/`, `accessibility/`). See [`CLAUDE.md`](CLAUDE.md) for the
full list. The operational, graded side of any live offering lives in
**Blackboard (the LMS)**, which is authoritative.

## Local development

```bash
quarto render     # build to _site/
quarto preview    # live preview
```

R code is shown as **static, non-executed** ```r fences, so the site
renders **fully with plain `quarto render` — no R required**.

No CI and no deploy pipeline in this repo. The combined site is assembled
and deployed by the hub repo (`matthewhester-site`). Local builds only
here; commits are deliberate and user-driven.
