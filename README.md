# Propensity vs. Incrementality in Digital Advertising

**CSCI E-109A · Fall 2026 · Milestone 2**

> **Research question:** Are the customers most likely to convert also the customers whose conversions advertising is most likely to cause?

## Project at a glance

A conversion observed after an ad is not necessarily a conversion caused by that ad. This project uses randomized treatment and control assignment in the [Criteo Uplift Prediction Dataset](https://ailab.criteo.com/criteo-uplift-prediction-dataset/) to examine whether targeting high conversion propensity or high estimated incremental response produces more incremental conversions under the same audience constraint.

| Item | Current status |
| --- | --- |
| Approved proposal | [`proposal.pdf`](proposal.pdf) |
| Milestone 2 data notebook | [`final_project.ipynb`](final_project.ipynb), executed Milestone 2 audit |
| Cleaned data and verified counts | 13,979,592 rows × 16 columns; notebook executed on the corrected v2.1 release |
| Revised proposal and slides | Pending Milestone 2 analysis |

## Milestone 2 scope

The notebook downloads or reuses the corrected Criteo v2.1 release and documents file size, schema, numerical summaries, missingness, unusual values, class balance, feature scales, leakage, a cleaned table, and a revised question. It has been executed on the full dataset. Full EDA and baseline modeling are Milestone 3 work.

## Data and analysis guardrails

- The 12 anonymized features `f0`–`f11` are candidate pre-treatment predictors; their exact semantic meanings are unavailable.
- Treatment assignment is randomized. Preserve treatment and control rows when cleaning so the comparison remains valid.
- Advertising exposure and website visit occur after assignment and are **not** targeting features available before the decision. Keep them for descriptive or causal-design checks only.
- Conversion is rare. Report actual counts by treatment arm before choosing metrics or targeting policies.
- Do not report preliminary proposal counts as cleaned-data results until independently verified.

## Repository workflow

`mainline` is the working branch for the latest shared changes. `Abhi` is available for Abhi's separate work. Merge reviewed contributions into `mainline`.

## Deliverables

- Notebook: executable `.ipynb` with group number and member names at the top
- Revised proposal: 1–2 page PDF grounded in verified cleaned data
- Presentation slides: PDF for an 8–10 minute presentation

The full source file is stored locally at `data/criteo-research-uplift-v2.1.csv.gz` and excluded from Git because of its size. The notebook can download and verify it on another machine. The original approved proposal is included; revised proposal and slides are pending.

## Run locally

From this folder, run `uv sync` and `uv run jupyter lab`, then open `final_project.ipynb` and run all cells. The environment is declared in [`pyproject.toml`](pyproject.toml). The notebook uses only NumPy, pandas, and Matplotlib. Fill in the Canvas group number and member names before submission.
