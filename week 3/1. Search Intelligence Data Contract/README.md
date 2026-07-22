# Week 3 — Assignment 1: Search Intelligence Data Contract

This directory contains the executed deliverables for **Week 3 Assignment 1: Search Intelligence Data Contract**.

## Deliverables

- **[w03_data_contract.ipynb](w03_data_contract.ipynb)**
  - **Data Contract (5 Answers)**:
    1. *Grain*: 1 Row = 1 Pseudonymized Content Item (`content_id`) / Client (`client_id`) over trailing 90-day observation window.
    2. *Table*: `data/raw/content_refresh_anonymized.csv` (30,000 rows).
    3. *Window*: Trailing 90-day pre-decision feature window (`impressions_90d`, `days_since_last_update`, `avg_position`, `ctr`, `engagement_rate`).
    4. *Target*: Proxy label `is_declining_label = (trend_direction == "down")` to score refresh priorities.
    5. *Deliberately Excluded*: `trend_pct` & `trend_direction` excluded from features to prevent target leakage.
  - **Verification Queries**:
    - *Grain Check*: Unique `content_id` grain proven (`max_dups == 1`).
    - *Row Count & Span*: 30,000 rows across content aged 90d to 502d.
    - *Availability Check*: `IS TRUE` filter (`impressions_90d > 0` AND `content_age_days >= 90`) verified with 30,000 surviving rows (100% survival on starter slice).
  - **5-Feature Frame**: `log_impressions_90d`, `days_since_last_update`, `avg_position`, `ctr`, `engagement_rate` (each accompanied by an availability statement).
  - **Deliberate Leakage Trap Experiment**: Tested adding `trend_pct` to feature inputs—demonstrating artificial metric jump and subsequent removal to preserve honest Precision@50 (0.440/0.740).
  - **Data Limitations**: Documented unbalanced client tracking histories and observational dataset boundaries.
