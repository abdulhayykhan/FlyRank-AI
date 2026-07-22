# Week 2 — Assignment 1: Frame Your Lane as an ML Task

This directory contains the executed deliverables for **Week 2 Assignment 1: Frame Your Lane as an ML Task**.

## Deliverables

- **[w02_ml_task_framing.ipynb](w02_ml_task_framing.ipynb)**
  - **ML Task Type**: Binary Classification & Priority Ranking (Scoring)
  - **Target Label**: `is_declining_label = (trend_direction == "down")` derived from observed traffic outcomes.
  - **Primary Success Metric**: Precision@50 (evaluating top 50 editorial recommendations).
  - **Unit of Analysis**: 1 Row = 1 Pseudonymized Content Item (`content_id`) / Client (`client_id`) over 90-day observation window.
  - **ML vs Rule Lift**: Random Forest Precision@50 (0.740) vs Static Rule (0.240) delivers a 3.08x empirical lift.
