# Are We Targeting the Wrong Customers?

### Propensity vs. incrementality in digital advertising

**COMPSCI 1090A · Fall 2026 · Project Group 4**

Abhi Gunasekar · Lily Nguyen · Matthew Surprenant · Parth Harish

> **Project question:** Does advertising correlate to a statistically significant difference on conversion among those who are exposed to advertisements?

An ad can precede a conversion without causing it. We use randomized treatment and control data to distinguish customers likely to convert anyway from customers whose conversion may be caused by advertising. The immediate Milestone 2 goal is to establish a trustworthy, usable table and a question the data can answer. Modeling and full exploratory analysis belong to Milestone 3.

## Start here

| File | Purpose | Status |
| --- | --- | --- |
| [`final_project.ipynb`](final_project.ipynb) | Download, load, describe, audit, and clean the corrected Criteo dataset; state the revised question | Complete and executed |
| [`proposal.pdf`](proposal.pdf) | Original approved project proposal | Available |
| Revised proposal PDF | Update the question, data, findings, and modeling plan | To prepare |
| Presentation slides PDF | Explain the data decisions and next steps to the project TF | To prepare |
| [`pyproject.toml`](pyproject.toml) and [`uv.lock`](uv.lock) | Reproducible Python environment | Available |

The source is the [Criteo Uplift Prediction Dataset](https://ailab.criteo.com/criteo-uplift-prediction-dataset/), using its [corrected v2.1 file](https://huggingface.co/datasets/criteo/criteo-uplift). The verified, 311.4 MB compressed file is stored locally in `data/` and ignored by Git. The notebook downloads and verifies it when needed.

## What the data established

| Finding | Implication |
| --- | --- |
| **13,979,592 users × 16 columns** after cleaning; no rows removed | The full randomized table is available for the Milestone 2 audit. |
| Twelve anonymized numerical features, plus treatment assignment, exposure, visit, and conversion | Feature meanings and measurement timing remain limitations to discuss with the TF. |
| No missing or nonfinite feature values; binary fields contain only 0 and 1 | No imputation or row deletion was needed. Unusual anonymized values were retained because their natural units are unknown. |
| **40,774 conversions (0.292%)**: 36,711 among 11,882,655 treated users; 4,063 among 2,096,937 controls | Conversion is rare, so accuracy alone would obscure model quality. Treatment allocation is unequal and must be accounted for in policy evaluation. |
| Exposure and visit occur after assignment; conversion is the outcome | These fields are excluded from pre-ad targeting predictors to avoid information leakage. |
| A seeded **5,000,000-user** random sample retains **14,494 conversions**, including 1,442 controls | This supports laptop-scale modeling while preserving the observed class and treatment proportions. |

The approved-project list marks the project **Approved** and advises a laptop-sized random sample with enough conversions. Criteo's privacy-related subsampling limits claims about the original advertisers' population-wide return.

## Milestone 2 checklist

**Deadline:** Friday, **November 13, 2026, 9:59 pm ET**, or the start of the TF presentation if earlier. The submission window closes at 10:00 pm; late days do not apply. One group member must upload **all three files together**. A replacement submission must include all three again.

### Notebook: data wrangling and project redefinition

- [x] Begin with Canvas group number and all four member names.
- [x] Download or load the actual source data and report total file size.
- [x] Define one row and every column; report shape, data types, and numerical summaries including mean, minimum, and maximum.
- [x] Measure missingness for every column, inspect treatment-arm patterns, and explain the decision to retain all rows.
- [x] Check unusual and nonfinite values, binary validity, and numerical feature ranges; explain why anonymized extremes are retained.
- [x] Report conversion class counts and treatment/control counts; identify severe class imbalance.
- [x] Identify post-decision fields and exclude them from proposed targeting predictors.
- [x] Produce a cleaned, usable table and a reproducible random analysis sample.
- [x] Include clearly titled plots with labeled axes for data understanding.
- [x] State a testable revised question and explain why the data support it.
- [x] Execute and validate the notebook with no saved error outputs.

### Revised proposal: one to two pages, PDF

- [ ] Explain the revised question and how the data confirmed or changed the original proposal.
- [ ] Link the source and give the cleaned table's row and column counts.
- [ ] Summarize the findings that affect the plan: rare conversions, leakage, sample size, anonymization, and source limitations.
- [ ] Specify proposed features, models, and held-out evaluation at equal audience sizes, with uncertainty.
- [ ] Confirm the approved-project status and reflect the staff's sampling and interpretation caveats.

### Presentation and submission

- [ ] Arrange the TF presentation for the week of November 9; allow 8–10 minutes presenting and about 10 minutes for discussion.
- [ ] Ensure every member attends and speaks for roughly the same amount of time.
- [ ] Make numbered slides with one main point each and readable, labeled plots.
- [ ] Cover the question, source and unit of observation, data size and columns, cleaning decisions, revised question, staff caveats, and member next steps.
- [ ] Export the slides and revised proposal as PDFs.
- [ ] Upload the **slides PDF, revised proposal PDF, and notebook `.ipynb`** in one Canvas submission before the applicable deadline.

## Run the notebook

From this directory:

```bash
uv sync
uv run jupyter lab
```

Open `final_project.ipynb` and run all cells. The first run downloads the source if it is absent and verifies its SHA-256 hash. The source file is deliberately excluded from Git because of its size. `mainline` holds the latest shared work; `Abhi` is currently synchronized with it.
