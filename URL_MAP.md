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

### Legacy pages with no 1:1 successor — now redirected to the closest fit (2026-07-10 closeout)

These old pages had no one-to-one successor in the new build; each now redirects (Quarto `aliases`) to its
closest documented successor, so the old URL resolves instead of 404-ing:

| Old URL | → Successor (closest topic) | Note |
|---|---|---|
| `labs/lab-11-robust-regression-versus-least-squares.html` | `notes/week-11-robust-regression-ideas.html` | robust regression is now a **note**, not a lab |
| `resources/resampling-guide.html` | `resources/method-comparison-guide.html` | resampling how-to folded into the method-comparison guide |
| `resources/robustness-and-outliers-guide.html` | `notes/week-10-robust-summaries-outliers.html` | robustness guidance folded into Week 10 + the guide |

New pages with no old equivalent (net-new, no redirect needed): `labs/lab-03-rank-methods.html`,
`resources/project-guidance.html`, `resources/reading-list.html`, `resources/setup.html`.

**Total redirects now generated: 16** (8 renamed notes + 5 restructured labs/resources + these 3). No known
legacy URL 404s.

## Accessibility inventory (rendered)

A full scan of the complete rendered `_site` (47 HTML pages incl. the 16 redirect stubs) finds **147
`<img>` tags, all 147 with a non-empty `alt` attribute — 0 missing, 0 empty.** This is the rendered-HTML
complement to the source-level `check_accessibility_static_lint` (a `.qmd` line parser that does not scan
rendered HTML). It is **presence evidence only**: alt-text **quality/adequacy and the assistive-technology /
contrast pass remain human-reviewed** (*present ≠ adequate*). Recorded in the build's
`_state/accessibility_status.md` (`rendered_alt_inventory: complete`).

## Deploy note & rollback

This branch (`release/resampling-refresh-2026-07-10`) is a **local release candidate only — not pushed, not
deployed**. `main` is untouched at `9a8189f`. Deployment is the hub-workflow + human step: after a human
approves, promote/merge the branch to `main`, push, and run the hub (`matthewhester-site`) `publish.yml` to
assemble and deploy — a course-repo push alone does not deploy.

**Rollback — prefer non-destructive over rewriting published history:**

- **Before promotion (nothing shared yet):** the release is isolated on its branch and `main` is unchanged
  at `9a8189f` — simply do not promote, or delete/reset the *local* branch. Nothing is published, so there
  is nothing to undo.
- **After promotion (merged, pushed, and/or deployed = shared history):** do **not** `git reset --hard` or
  force-push a shared branch. Instead, either
  1. **`git revert`** the promotion commit — `git revert -m 1 <merge-commit>` (or revert the range) — which
     adds a *new* commit restoring the prior content, then re-run the hub `publish.yml`; **or**
  2. **redeploy the tagged prior release** — the pre-refresh state is preserved at tag
     `rollback/pre-resampling-refresh-2026-07-10` (= `9a8189f`); check it out into the deploy source and
     re-run the hub.

  Both keep published history append-only. Reserve `reset --hard` / force-push for a purely local,
  never-shared branch only.
