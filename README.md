# Hillstrom Email Marketing — Recency-Based Targeting

A causal analysis of the [Hillstrom Email Marketing Experiment](https://blog.minethatdata.com/2008/03/minethatdata-e-mail-analytics-and-data.html), using the randomized A/B test to estimate whether the incremental revenue effect of email marketing varies with how recently a customer last purchased — and to translate the per-recency-bin lifts into a per-bin targeting policy under an assumed $0.01 send cost.

## Research question

**Accessible:** Does the causal effect of email marketing on revenue depend on how recently a customer last purchased, and what does this imply about how retailers should allocate promotional campaigns?

**Operational:** For each recency-based customer group (Warm, Cooling, Dormant, Very dormant), should the retailer send the Mens E-Mail campaign, the Womens E-Mail campaign, or no email, in order to maximize incremental profit at an assumed $0.01 per email send cost?

## Dataset

64,000 customers randomly assigned in equal thirds to three arms — `No E-Mail` (control), `Mens E-Mail`, `Womens E-Mail`. Outcomes (`visit`, `conversion`, `spend`) are measured over a two-week post-campaign window. See [data/hillstrom_data.csv](data/hillstrom_data.csv).

## Project tree

```
hillstrom/
├── README.md                       <- this file
├── implement_draft_analyses.qmd    <- runner: executes every analysis in plan_of_attack.qmd
├── data/
│   └── hillstrom_data.csv          <- raw experiment data (64,000 rows × 12 cols)
├── deliverables/                   <- files for submission (qmd sources + rendered PDFs)
│   ├── README.md
│   ├── question_and_dataset.qmd
│   └── plan_of_attack.qmd
├── plots/                          <- figures rendered by implement_draft_analyses.qmd
├── tables/                         <- per-analysis CSV tables
└── output/
    └── recency_results_summary.md  <- auto-generated headline numbers
```

## Folder reference

- **`data/`** — input data only. The single CSV [hillstrom_data.csv](data/hillstrom_data.csv) holds all 64,000 customer rows with pre-treatment covariates and post-experiment outcomes.

- **`deliverables/`** — Quarto source files for the assignment write-ups (`question_and_dataset.qmd`, `plan_of_attack.qmd`) plus their rendered PDFs. PDFs are gitignored to avoid bloating the repo; see [deliverables/README.md](deliverables/README.md) for the link to the Dropbox folder where the rendered PDFs live. Or I can just send it upon request.

- **`plots/`** — figures produced by [implement_draft_analyses.qmd](implement_draft_analyses.qmd). Includes the cell-counts diagnostic, the baseline overall-effects bar chart, faceted-bar versions of Figures 1–2 (per-bin lift on spend, visit, conversion), the two policy-recommendation variants (Option A verdict-titled bars, Option B incremental-profit bars), and the covariate-balance check.

- **`tables/`** — eight CSVs corresponding to Tables 1–8 in the plan: raw summary stats, per-bin × arm cell counts, overall treatment effects, per-bin spend lifts, the funnel decomposition (visit / conversion / spend), the policy recommendations, the winsorized-robustness re-run, and the covariate-balance check.

- **`output/`** — auto-generated artifacts from the runner. [recency_results_summary.md](output/recency_results_summary.md) holds the headline numbers in plain Markdown for inclusion in write-ups.

## Reproducing the analysis

[implement_draft_analyses.qmd](implement_draft_analyses.qmd) is the runner. It executes every analysis described in [deliverables/plan_of_attack.qmd](deliverables/plan_of_attack.qmd) end-to-end: loading the CSV, constructing recency bins, estimating per-bin treatment effects, generating all figures into `plots/` and tables into `tables/`, and writing the headline summary to `output/recency_results_summary.md`.

Note: These are draft analyses. Not set in stone.


Required R packages: `tidyverse`, `scales`, `patchwork`.