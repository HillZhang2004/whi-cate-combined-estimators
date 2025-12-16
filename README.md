# whi-cate-combined-estimators

Code from my SRP25 work with Prof. Evan Rosenman (May 2025 to Sep 2025). This repository contains Quarto and R scripts for working with WHI (Women’s Health Initiative) randomized trial and observational cohorts to:

1. clean and harmonize WHI RCT and observational cohorts,
2. estimate CATEs from each source, and
3. combine estimates using empirical Bayes shrinkage (λ-URE, λ₂) and moment-matching baselines.

## Highlights

- End-to-end, reproducible Quarto workflow with explicit validation and sanity checks
- Separate pipelines for observational CATE estimation and RCT bootstrap uncertainty
- Combined estimators that trade off bias and variance in a controlled way
- Evaluation artifacts focused on calibration and out-of-sample behavior

## Repository structure

- `code/0924/`
  - `0718 Obs CATE.qmd`  
    Observational CATE estimation pipeline
  - `0718 RCT Bootstrap.qmd`  
    RCT bootstrap pipeline for uncertainty and benchmarking
  - `0718combined_estimator.qmd`  
    Combined estimators (λ-URE, λ₂, moment matching) plus calibration and OOF evaluation
- `outputs/0924/`
  - `plots/`  
    Grouped plots (age, BMI, smoking, etc.)
  - `*.pdf`, `*.csv`  
    Summary-level tables and reporting artifacts used for evaluation and writeups

## Data and privacy

This repository does **not** include WHI participant-level records or identifiers.

- If you use WHI data locally, keep it outside this repo. The `.gitignore` is configured to avoid tracking common local data artifacts.
- The `outputs/` folder is intended to contain **summary-level** evaluation artifacts (plots and aggregate tables), not participant-level records.
- If you are covered by a WHI data use agreement, confirm whether derived outputs (plots, summary tables) are allowed to be shared publicly. If you are not sure, remove `outputs/` from the public repo.

## Requirements

- R (4.x recommended)
- Quarto (for rendering the `.qmd` files)

Package requirements depend on your local environment, but typical dependencies include `tidyverse`, `data.table`, `ggplot2`, and any modeling packages used inside the scripts.

## How to run (requires local WHI data)

1. Open the relevant Quarto file in `code/0924/`
2. Set local paths and any required parameters near the top of the file
3. Render with Quarto

Examples:

```bash
# Combined estimator report
quarto render "code/0924/0718combined_estimator.qmd"

# Observational CATE pipeline (note the filename has spaces)
quarto render "code/0924/0718 Obs CATE.qmd"

# RCT bootstrap pipeline (note the filename has spaces)
quarto render "code/0924/0718 RCT Bootstrap.qmd"
