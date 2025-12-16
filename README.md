# whi-cate-combined-estimators

Code from my SRP25 work with Prof. Evan Rosenman (May 2025 to Sep 2025). This repository contains Quarto and R scripts for:
1) cleaning and harmonizing WHI RCT and observational cohorts,
2) estimating CATEs from each source, and
3) combining estimates using empirical Bayes shrinkage (λ-URE, λ₂) and moment-matching baselines.

## Highlights
- End-to-end, reproducible Quarto workflow with explicit validation and sanity checks
- Separate pipelines for observational CATE estimation and RCT bootstrap uncertainty
- Combined estimators that trade off bias and variance in a controlled way
- Evaluation artifacts focused on calibration and out-of-sample behavior

## Repository structure
- `code/0924/`
  - `0718 Obs CATE.qmd`  
  - `0718 RCT Bootstrap.qmd`  
  - `0718combined_estimator.qmd`
- `outputs/0924/`
  - `plots/` (grouped plots such as age, BMI, smoking, etc.)
  - PDFs and summary tables used for evaluation and reporting

## Data and privacy
This repository does NOT include any WHI participant-level data or identifiers.

If you are using WHI data locally, keep it outside this repo. The `.gitignore` is configured to avoid tracking common local data artifacts.

Important: if you are covered by a WHI data use agreement, confirm whether derived outputs (plots, summary tables) are allowed to be shared publicly.

## How to run (requires local WHI data)
1) Open the relevant Quarto file in `code/0924/`
2) Set local paths and any required parameters at the top of the file
3) Render:
```bash
quarto render "code/0924/0718combined_estimator.qmd"

Contact

Hill Zhang
GitHub: https://github.com/HillZhang2004

Email: hillzhang.ai@gmail.com
