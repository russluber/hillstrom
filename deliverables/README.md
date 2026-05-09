# Deliverables

Files submitted for the assignment. The `.qmd` sources are tracked in this repo; the rendered PDFs are gitignored to avoid bloating the repo and instead live in a Dropbox folder.

## Rendered PDFs

> **Dropbox link:** TBD

## Sources tracked here

- [`question_and_dataset.qmd`](question_and_dataset.qmd) — Question and Dataset write-up.
- [`plan_of_attack.qmd`](plan_of_attack.qmd) — Plan of Attack write-up. Defines Sections 1–3 (raw data description, sample construction plan, analysis plan including the four analyses and three robustness checks). The runner [`../implement_draft_analyses.qmd`](../implement_draft_analyses.qmd) executes everything described here.

## Rendering

From the project root:

```bash
quarto render deliverables/plan_of_attack.qmd
quarto render deliverables/question_and_dataset.qmd
```

Output PDFs land in this folder, then get uploaded to the Dropbox link above.
