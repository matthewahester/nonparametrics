# URL continuity map — resampling refresh release candidate (2026-07-10)

This release replaces the previous Nonparametrics public source with the refreshed
`resampling-nonparametric-robust-methods` build (fixed public-code + native MathML). The site slug and
`site-url` (`https://matthewhester.com/nonparematrics/`) are unchanged, and the root pages keep their URLs:

| Root page | URL | Status |
|---|---|---|
| Home | `index.html` | unchanged |
| Syllabus | `syllabus.html` | unchanged |
| Schedule | `schedule.html` | unchanged |

## Handled by redirect (Quarto `aliases` → JS redirect stubs at the old URL)

The old URL 301-style redirects (client-side) to the new page; existing bookmarks keep working.

### Notes (renamed, same topic)
| Old URL | → New page |
|---|---|
| `notes/week-01-why-assumption-light-methods.html` | `notes/week-01-why-assumption-light.html` |
| `notes/week-02-order-statistics-ranks-and-empirical-distributions.html` | `notes/week-02-order-statistics-ranks-ecdf.html` |
| `notes/week-07-rank-based-one-sample-and-paired-methods.html` | `notes/week-07-rank-based-one-sample-paired.html` |
| `notes/week-09-categorical-and-ordinal-outcomes.html` | `notes/week-09-categorical-ordinal-outcomes.html` |
| `notes/week-10-robust-summaries-and-outliers.html` | `notes/week-10-robust-summaries-outliers.html` |
| `notes/week-12-comparing-parametric-and-nonparametric-conclusions.html` | `notes/week-12-comparing-parametric-nonparametric.html` |
| `notes/week-13-simulation-study-of-method-behavior.html` | `notes/week-13-simulation-study-method-behavior.html` |
| `notes/week-14-applied-robust-methods-report-workshop.html` | `notes/week-14-applied-robust-methods-report.html` |

Notes with unchanged slugs (no redirect needed): week-03, week-04, week-05, week-06, week-08, week-11, week-15.

### Labs & resources (restructured — redirected to the closest same-topic successor)
| Old URL | → New page (closest topic) |
|---|---|
| `labs/lab-04-build-a-randomization-test.html` | `labs/lab-01-permutation-test.html` |
| `labs/lab-05-bootstrap-the-median.html` | `labs/lab-02-bootstrap-ci.html` |
| `labs/lab-13-a-method-comparison-simulation.html` | `labs/lab-05-simulation-study.html` |
| `resources/method-chooser.html` | `resources/method-comparison-guide.html` |
| `resources/methods-glossary.html` | `resources/notation-and-glossary.html` |

## Material breakage — NO direct successor (HUMAN DECISION at deploy)

These old pages have no one-to-one successor in the new build. They are currently **not** redirected (they
would 404). Recommended targets if a redirect is wanted — add an `aliases:` entry to the suggested page and
re-render, OR accept the 404:

| Old URL (would 404) | Suggested redirect target | Note |
|---|---|---|
| `labs/lab-11-robust-regression-versus-least-squares.html` | `notes/week-11-robust-regression-ideas.html` | robust regression is now a **note**, not a lab |
| `resources/resampling-guide.html` | `resources/method-comparison-guide.html` | resampling how-to folded into the method-comparison guide |
| `resources/robustness-and-outliers-guide.html` | `notes/week-10-robust-summaries-outliers.html` | robustness guidance folded into Week 10 + the guide |

New pages with no old equivalent (net-new, no redirect needed): `labs/lab-03-rank-methods.html`,
`resources/project-guidance.html`, `resources/reading-list.html`, `resources/setup.html`.

## Deploy note

This branch is a **local release candidate only** — not pushed and not deployed. Deployment is the
hub-workflow + human step (see the repository's release controls). Roll back with the tag
`rollback/pre-resampling-refresh-2026-07-10`.
