# Week 4 — Assignment 1: Baseline Action Score and Top-10 Review

This directory contains the executed deliverables for **Week 4 Assignment 1: Baseline Action Score and Top-10 Review**.

## Deliverables

- **[w04_baseline_score.ipynb](w04_baseline_score.ipynb)**
  - **Signal Audit**:
    1. *Staleness (`days_since_last_update`)*: **CONFIRMED** — Content updated >180 days ago exhibits elevated decline rate (54.5%+ vs 48% fresh).
    2. *Position Tier & CTR (`position_tier`)*: **CONFIRMED** — Page 1 and striking distance content possess high commercial exposure where decay is critical.
  - **Heuristic Baseline Score Formula**: `baseline_score = stale_flag * visible_flag * log1p(impressions_90d) * (1.0 + 0.5 * striking_flag)`
  - **Reason Codes & Action Labels**: `stale_visible_page`, `page_one_decay_risk`, `low_ctr_visible_page` $\rightarrow$ `content_refresh_audit`, `title_meta_rewrite`, `monitor_performance`.
  - **Queue Output**: Generated and written to `work/outputs/baseline_action_score.csv` from the notebook.
  - **Top-10 Skeptic Risk Audit**: Audited top 10 ranked recommendations with explicit risk notes on what would make each recommendation wrong (e.g. seasonal demand shifts, deep position noise, intentional URL migrations).
  - **Baseline Benchmark**: Baseline Precision@50 = **0.340** (Precision@20 = **0.350**).
