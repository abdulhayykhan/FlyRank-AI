# Week 8 — Assignment 1: Ship the Paper

This directory contains the executed deliverables for **Week 8 Assignment 1: Ship the Paper**.

## Deployed Research Paper URL
- **Live Paper Website**: [https://abdulhayykhan.github.io/FlyRank-AI/](https://abdulhayykhan.github.io/FlyRank-AI/)
- **URL Record File**: `submission/paper_url.txt`

## Deliverables

- **[capstone.ipynb](capstone.ipynb)**
  - **Title & Abstract**: 5-sentence paper abstract (question $\rightarrow$ dataset $\rightarrow$ method $\rightarrow$ result $\rightarrow$ decision-support).
  - **Complete Research Synthesis**:
    1. *Introduction & Problem Statement*: Enterprise content decay challenge.
    2. *Data Contract*: 79M-row production dataset slice (30,000 items), unit of analysis, observation windows, and leakage exclusions (`trend_pct`).
    3. *Methodology & Leakage Audit*: Client-grouped holdouts (`GroupShuffleSplit` on `client_id`) and 9-point leakage checklist.
    4. *Results*: Benchmark comparison table (Random Forest Precision@50 = **0.740** vs Baseline = **0.340**; **2.18x directional lift**).
    5. *Limitations*: Disclosed observational bounds, enterprise B2B scope, and technical SEO exclusions.
    6. *Ranked Recommendations*: Content action playbook with archetype-to-action matrix and strict 🛑 No-Go automation rules.
    7. *Reproducibility*: Links to all weekly notebooks, random seeds, and open-source GitHub repository.
    8. *Acknowledgments & Data Credit*: **"Built on the [FlyRank](https://flyrank.ai) ML Internship dataset."**
