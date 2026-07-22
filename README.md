# 🚀 FlyRank AI Machine Learning Internship — Capstone Repository

[![Live Paper](https://img.shields.io/badge/Live%20Paper-GitHub%20Pages-blue?style=for-the-badge&logo=github)](https://abdulhayykhan.github.io/FlyRank-AI/)
[![Dataset](https://img.shields.io/badge/Dataset-Hugging%20Face-orange?style=for-the-badge&logo=huggingface)](https://huggingface.co/datasets/FlyRank/internship-warehouse)
[![Data Source](https://img.shields.io/badge/Data%20Credit-FlyRank.ai-green?style=for-the-badge)](https://flyrank.ai)

**Author:** Abdul Hayy Khan  
**Track:** Machine Learning Internship (8-Week Foundations & Build Phase)  
**Selected Lane:** **Lane 2 — Refresh / Content Opportunity Scoring**  
**Deployed Research Paper:** [https://abdulhayykhan.github.io/FlyRank-AI/](https://abdulhayykhan.github.io/FlyRank-AI/)  

---

## 📌 Executive Summary

This repository contains the complete 8-week capstone research and engineering codebase for the **FlyRank AI Machine Learning Internship**. 

Evaluating a 79-million-row production search intelligence warehouse slice (30,000 pseudonymized enterprise content items), we formulate a machine learning priority scoring framework to identify and rank organic search traffic decay before major traffic loss occurs.

### Headline Results:
- **Client-Grouped Holdout Validation (`GroupShuffleSplit` on `client_id`):** Tested across unseen enterprise client domains to prevent domain data leakage.
- **Model vs Baseline Performance:**
  - *Week 4 Heuristic Baseline Rule:* Precision@50 = **0.340** | ROC-AUC = **0.627**
  - *Random Forest Classifier (n=100):* Precision@50 = **0.740** | ROC-AUC = **0.750**
- **Empirical Lift:** Achieved an **observed 0.740 Precision@50** (a **2.18x directional lift** over the heuristic baseline).

---

## 📂 Repository Architecture & Weekly Deliverables

```text
FlyRank-AI/
├── docs/                                 # GitHub Pages Root (Live Web Paper)
│   └── index.html                        # Published Research Paper Website
├── submission/
│   └── paper_url.txt                     # Deployed URL Record File
├── week 1/
│   ├── 1. Run the Starter Notebooks/    # Week 1 Assignment 1 (01 & 02 Notebooks + Reports)
│   └── 2. Research Question and Lane/   # Week 1 Assignment 2 (w01_research_question.ipynb)
├── week 2/
│   ├── 1. Frame Your Lane as ML Task/   # Week 2 Assignment 1 (w02_ml_task_framing.ipynb)
│   └── 2. VIDEO ML Intro Workshop/       # Week 2 Assignment 2 (ML Systems Summary & Learnings)
├── week 3/
│   └── 1. Search Intelligence Contract/ # Week 3 Assignment 1 (w03_data_contract.ipynb)
├── week 4/
│   └── 1. Baseline Action Score & Audit/ # Week 4 Assignment 1 (w04_baseline_score.ipynb)
├── week 5/
│   └── 1. Capstone Modeling Lane/       # Week 5 Assignment 1 (w05_model.ipynb)
├── week 6/
│   └── 1. Validation & Claim Audit/     # Week 6 Assignment 1 (w06_validation_audit.ipynb)
├── week 7/
│   └── 1. Content Action Playbook/       # Week 7 Assignment 1 (w07_action_playbook.ipynb)
├── week 8/
│   └── 1. Ship the Paper/                # Week 8 Assignment 1 (capstone.ipynb)
└── work/
    ├── figures/                          # Reusable Paper Figures (Precision@K, Feature Importances)
    ├── notebooks/                        # Primary Executed Jupyter Notebooks
    └── outputs/                          # Metrics Receipts (model_metrics.json, action queues)
```

---

## 🗺️ Weekly Curriculum & Roadmap Overview

| Week | Assignment Title | Key Deliverables & Summary |
|---|---|---|
| **Week 1** | **Starter Notebooks & Research Question** | Executed discovery & decision tree notebooks; established Lane 2 framing backed by 3 dataset metrics. |
| **Week 2** | **ML Task Formulation & Systems Map** | Mapped Lane 2 as Binary Classification + Priority Ranking ($P(\text{decline}=1)$ sorted for Precision@50). Summarized video workshop. |
| **Week 3** | **Search Intelligence Data Contract** | Formulated 5 plain-words contract answers, executed 3 fact queries, built 5-feature frame, and ran deliberate leakage trap (`trend_pct`). |
| **Week 4** | **Baseline Action Score & Top-10 Audit** | Audited staleness and position signals (CONFIRMED), built transparent heuristic baseline rule, and executed top-10 skeptic risk audit. |
| **Week 5** | **Capstone Modeling Lane** | Trained Logistic Regression, Decision Tree, and Random Forest models on `GroupShuffleSplit` client holdouts (Random Forest Precision@50 = **0.740**). |
| **Week 6** | **Validation & Research Claim Audit** | Audited research paper findings, compared Random vs Grouped split gap (+8.0% overestimation), ran 9-point leakage checklist, and rewrote claims. |
| **Week 7** | **Content Action Playbook** | Built Archetype $\rightarrow$ Action matrix, defined human review rules and strict 🛑 No-Go automation list, exported metric JSON receipts and paper charts. |
| **Week 8** | **Ship the Paper & Deploy** | Assembled 9-section research paper, executed `capstone.ipynb`, deployed live to GitHub Pages, and recorded URL in `submission/paper_url.txt`. |

---

## ⚙️ Reproducibility & Local Execution

To reproduce the analysis, models, and paper artifacts locally:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/abdulhayykhan/FlyRank-AI.git
   cd FlyRank-AI
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run notebooks:**
   Execute notebooks sequentially under `work/notebooks/`:
   ```bash
   jupyter lab work/notebooks/capstone.ipynb
   ```

---

## 🤝 Acknowledgments & Data Credit

Built on the **[FlyRank](https://flyrank.ai)** ML Internship dataset. Special thanks to the FlyRank AI team and instructors for providing access to production search intelligence datasets and guidance throughout the capstone lifecycle.
