# Week 5 — Assignment 1: Capstone Modeling Lane

This directory contains the executed deliverables for **Week 5 Assignment 1: Capstone Modeling Lane**.

## Deliverables

- **[w05_model.ipynb](w05_model.ipynb)**
  - **Method Choice**: Compared Logistic Regression, Decision Tree (max_depth=3), and Random Forest against Week 4 heuristic baseline.
  - **Honest Group Validation Split**: `GroupShuffleSplit` on `client_id` (80% train / 20% test holdout across 6 held-out clients).
  - **Model vs Baseline Comparison Table (Test Holdout)**:
    - *Week 4 Heuristic Baseline*: Precision@20 = **0.350** | Precision@50 = **0.340** | ROC-AUC = **0.627**
    - *Logistic Regression*: Precision@20 = **0.400** | Precision@50 = **0.400** | ROC-AUC = **0.700**
    - *Decision Tree (d=3)*: Precision@20 = **0.650** | Precision@50 = **0.540** | ROC-AUC = **0.742**
    - *Random Forest (n=100)*: Precision@20 = **0.750** | Precision@50 = **0.740** | ROC-AUC = **0.750**
  - **Feature Importance & Error Analysis**:
    - Top features: `days_since_last_update` (28.4%), `avg_position` (22.1%), `impressions_90d` (19.5%), `ctr` (12.3%).
    - Conducted a concrete false-positive error audit analyzing stable/growing pages that received high model scores due to staleness/position signals.
