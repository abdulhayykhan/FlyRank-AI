# Week 6 — Assignment 1: Validation and Research Claim Audit

This directory contains the executed deliverables for **Week 6 Assignment 1: Validation and Research Claim Audit**.

## Deliverables

- **[w06_validation_audit.ipynb](w06_validation_audit.ipynb)**
  - **Research Paper Audit Questions**:
    1. *Finding 1 (+34% traffic recovery)*: Where does the label come from and was recovery measured against an un-updated control group to control for seasonality?
    2. *Finding 2 (78% Precision@50)*: Was evaluation conducted using client-grouped holdout splits (`GroupKFold`) or naive random splits that leak domain baselines?
  - **Before vs After Validation Split Audit**:
    - *Random Split (Naïve / Overfitting)*: Precision@20 = **0.850** | Precision@50 = **0.820** | ROC-AUC = **0.812**
    - *Client-Grouped Split (Honest Holdout)*: Precision@20 = **0.750** | Precision@50 = **0.740** | ROC-AUC = **0.750**
    - *Overestimation Gap*: Random split overestimates Precision@50 by **+0.080 (+8.0%)** due to client domain leakage across split sets.
  - **9-Point Leakage Checklist**: Verified pre-decision observation window, zero target-derived features (`trend_pct` excluded), zero product flags, client-grouped splits, base rate benchmarks, and out-of-fold evaluation.
  - **Claim Rewrite**:
    - *Before*: "Our ML model guarantees 74% accuracy in predicting decline and driving traffic recovery."
    - *After*: "In client-holdout validation tests, the Random Forest model achieved an **observed 0.740 Precision@50** (a **2.18x directional lift** over the 0.340 baseline), providing **decision-support** to prioritize content items for editorial refresh review."
