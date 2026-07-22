# Week 7 — Assignment 1: Content Action Playbook

This directory contains the executed deliverables for **Week 7 Assignment 1: Content Action Playbook**.

## Deliverables

- **[w07_action_playbook.ipynb](w07_action_playbook.ipynb)**
  - **Archetype $\rightarrow$ Action Matrix**:
    1. *Archetype A (High-Exposure Stale Decay)*: `impressions_90d >= 1000` & `days_since_update >= 180` $\rightarrow$ `full_content_refresh` (`stale_high_traffic_decay`).
    2. *Archetype B (Striking Distance CTR Gap)*: `position 1.0-20.0` & `ctr < 1.0%` $\rightarrow$ `title_meta_ctr_rewrite` (`striking_distance_ctr_gap`).
    3. *Archetype C (Thin Content Staleness)*: `word_count < 800` & `days_since_update >= 90` $\rightarrow$ `depth_expansion_and_faq` (`thin_content_staleness`).
    4. *Archetype D (Low Volume / Deep SERP)*: `impressions_90d < 500` & `position > 30` $\rightarrow$ `monitor_or_prune` (`low_volume_deep_serp`).
  - **Intended Use & Operational Boundaries**:
    - Decision-support recommendation queue for human SEO strategists and editorial copywriters.
    - Observational correlations (not guaranteed causal recovery). Excludes off-page backlinks and technical crawl errors.
  - **Human Review Checklist & Strict No-Go List**:
    - Mandatory human review of search intent, active site migrations, and seasonality.
    - 🛑 **NO automated unassisted LLM text generation and publishing**.
    - 🛑 **NO automated 301 redirects, canonical modifications, or URL deletions**.
    - 🛑 **NO automated alterations on YMYL legal/medical compliance pages**.
  - **Data Drift & Monitoring Policy**: Retrain model if holdout Precision@50 drops below **0.600** or if Google SERP layout changes shift global CTR baselines.
  - **Exported Paper Artifacts**:
    - `work/outputs/action_playbook_queue.csv` (Actionable priority queue CSV)
    - `work/outputs/model_metrics.json` (Validated holdout metrics receipt JSON)
    - `work/figures/feature_importances.png` (Feature importance chart)
    - `work/figures/precision_at_k.png` (Precision@K curve)
