# VIDEO: Machine Learning — Intro to ML Systems: What ML Actually Solves Here w/ Mirza

**Video Link**: [https://youtu.be/aTxLqzQ5Isg](https://youtu.be/aTxLqzQ5Isg)  
**Session**: FlyRank ML Internship — Week 2 Live Workshop  

---

## Executive Summary

This workshop covers the foundational transition from simple heuristics to production machine learning systems. It outlines the core boundaries between AI, ML, Analytics, and Rules, details the end-to-end Machine Learning Loop, contrasts Supervised vs Unsupervised learning paradigms, and emphasizes the critical importance of generalization over memorization in real-world search intelligence systems.

---

## Key Learnings & Core Concepts

### 1. What ML Actually Solves Here
- **Beyond Fixed Rules**: Traditional search auditing relies on static heuristics (e.g. `days_since_last_update > 180`). These rules fail because content decay depends on non-linear interactions across traffic volume, ranking position tiers, click-through rates, and user engagement.
- **Decision Support System**: Machine learning does not replace human editors with a black box; it generates a probabilistic priority score ($P(\text{decline}=1)$) to allocate limited editorial review capacity (e.g. Top 50 review queue).

---

### 2. AI vs ML vs Analytics vs Rules

| Concept | Definition | Role in Search Intelligence |
|---|---|---|
| **Rules / Heuristics** | Hardcoded `if/else` conditional logic | Quick baseline to beat; transparent but brittle at scale. |
| **Analytics (EDA)** | Descriptive data aggregation and trend analysis | Explains *what happened* in past performance data. |
| **Machine Learning** | Statistical patterns learned automatically from feature vectors | Predicts *what is likely to happen* ($P(y=1\|X)$) to rank actions. |
| **Artificial Intelligence** | Broad umbrella including ML, optimization, and LLMs | End-to-end intelligent systems integrating prediction and workflow automation. |

---

### 3. The Machine Learning Loop

```text
Problem Framing ──► Data Contract ──► Feature Engineering ──► Baseline Rule ──► Model Training ──► Validation & Leakage Audit ──► Priority Queue Export
```

1. **Problem Framing**: Defining the decision, target, metric (Precision@50), and action before writing code.
2. **Data Sanitation & Contract**: Cleaning missing values, avoiding leakages, and establishing observable signal boundaries.
3. **Feature Engineering**: Creating domain-relevant signals (freshness tiers, log-transformed volume, CTR gaps).
4. **Baseline Creation**: Building a simple hand-rule baseline to prove ML value over static logic.
5. **Model Training & Evaluation**: Fitting statistical models (Logistic Regression, Decision Trees, Random Forests) and evaluating on client-holdout splits.
6. **Deployment & Monitoring**: Generating explainable reason codes for human editorial review.

---

### 4. Supervised vs Unsupervised Learning
- **Supervised Learning**: Models mapped from feature inputs $X$ to observed historical outcomes $y$ (e.g., predicting traffic decline for ranking review queues).
- **Unsupervised Learning**: Pattern discovery without explicit labels (e.g., clustering structured content into behavioral archetypes like "Rising Stars" or "Stale Traffic Anchors").

---

### 5. Generalization vs Overfitting
- **Overfitting / Memorization**: Occurs when a model memorizes training noise or leaks future outcome answers into features (e.g. including `trend_pct` when predicting `trend_direction`). The model looks perfect in-sample but fails completely in deployment.
- **Generalization**: The primary goal of ML systems—ensuring learned decision boundaries hold on unseen client holdout data (`GroupShuffleSplit` by `client_id`).

---

## Takeaway Summary
- **Start with the Decision**: Frame the business action before selecting a model.
- **Earn Complexity**: Always build and evaluate against a transparent baseline first.
- **Respect Data Leakage**: Features must be knowable *before* the decision point.
