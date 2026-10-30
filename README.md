# Propensity vs. Incrementality in Digital Advertising

**CSCI E-109A · Fall 2026 · Milestone 2**

> **Research question:** Are the customers most likely to convert also the customers whose conversions advertising is most likely to cause?

## Project at a glance

A conversion observed after an ad is not necessarily a conversion caused by that ad. This project uses randomized treatment and control assignment in the [Criteo Uplift Prediction Dataset](https://ailab.criteo.com/criteo-uplift-prediction-dataset/) to examine whether targeting high conversion propensity or high estimated incremental response produces more incremental conversions under the same audience constraint.

| Item | Current status |
| --- | --- |
| Approved proposal | [`proposal.pdf`](proposal.pdf) |
| Milestone 2 data notebook | [`final_project.ipynb`](final_project.ipynb), starter scaffold |
| Cleaned data and verified counts | Pending data acquisition and notebook execution |
| Revised proposal and slides | Pending Milestone 2 analysis |

## Milestone 2 scope

The notebook will document data acquisition, file size, row and column meanings, types, summary statistics, missingness, unusual values, class balance, feature scales, and leakage checks. It will conclude with a precise revised question. Full EDA and baseline modeling are Milestone 3 work.

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

Only the approved original proposal and notebook scaffold are currently included. The dataset is intentionally excluded from Git because of its size. See the [source](https://ailab.criteo.com/criteo-uplift-prediction-dataset/) for download details.
