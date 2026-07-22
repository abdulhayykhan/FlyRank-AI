# Week 8 — Assignment 2: Tell the Story (Showcase & Shareable Cuts)

This document contains the showcase storytelling assets, 5-minute demo outline, and shareable cuts for **Lane 2: Refresh / Content Opportunity Scoring**.

---

## 1. Case Study Framing (Inside Research Paper)
Our live research paper at [https://abdulhayykhan.github.io/FlyRank-AI/](https://abdulhayykhan.github.io/FlyRank-AI/) frames the core FlyRank enterprise search problem:
- **The Problem**: Enterprise digital publications manage thousands of indexable URLs. Over time, search intent evolves and algorithm layouts change—causing content to decay. Traditional quarterly audits rely on naive age thresholds (e.g. updating any page older than 180 days), producing high false-positive rates and wasting editorial budgets.
- **The Solution**: Machine learning content opportunity scoring that evaluates historical search impressions, average position trends, and staleness to rank refresh candidates by expected editorial ROI.

---

## 2. 5-Minute Showcase Demo Outline

```text
=== 5-MINUTE DEMO OUTLINE (WEEK 8 SHOWCASE) ===

[0:00 - 1:00] THE QUESTION & CASE STUDY
- Question: How can enterprise SEO teams prioritize decaying content before major organic traffic loss occurs?
- The Tension: Naive threshold rules (flagging all content >180 days old) fail because 48% of stale pages are still growing.

[1:00 - 2:00] DATA & HONEST VALIDATION
- Dataset: 79M-row production warehouse slice (30,000 enterprise content items).
- Split Design: Client-grouped holdout (GroupShuffleSplit on client_id) to prevent domain authority leakage across split sets.

[2:00 - 3:15] THE ONE CHART & HONEST RESULT
- One Chart: Precision@K Curve on held-out client domains.
- Result: Random Forest achieved 0.740 Precision@50 vs 0.340 Baseline Rule (2.18x directional lift).

[3:15 - 4:15] CONTENT ACTION PLAYBOOK & HUMAN RULES
- Playbook: Archetype-to-action matrix (stale high-traffic -> full refresh; position 1-20 CTR gap -> title/meta rewrite).
- Strict No-Go List: NO unassisted LLM publishing, NO automated 301 redirects, NO automated YMYL edits.

[4:15 - 5:00] REPRODUCIBILITY & DEPLOYED PAPER
- Live Research Paper: https://abdulhayykhan.github.io/FlyRank-AI/
- Open-Source GitHub Repository: https://github.com/abdulhayykhan/FlyRank-AI
```

---

## 3. Shareable Cut 1: Short Social Post (Methodology Focus)

> 🚀 **Excited to share my capstone research for the FlyRank AI Machine Learning Internship!**  
>  
> How do you catch organic search traffic decline in enterprise portfolios before major traffic loss happens? Static rules fail because age alone doesn't mean a page is dying.  
>  
> Evaluating a 79M-row production dataset slice (30,000 enterprise URLs), I built a Random Forest Content Opportunity Scoring system using client-grouped holdout validation (`GroupShuffleSplit` on `client_id`) to prevent domain leakage.  
>  
> 📈 **Result:** Achieved **0.740 Precision@50** (a **2.18x directional lift** over heuristic baselines) while enforcing strict human-in-the-loop editorial boundaries.  
>  
> 📄 Read the live paper & playbook: https://abdulhayykhan.github.io/FlyRank-AI/  
> 📦 Code & notebooks: https://github.com/abdulhayykhan/FlyRank-AI  
>  
> #MachineLearning #DataScience #SEO #FlyRank #AI #Python  

---

## 4. Shareable Cut 2: 3-Sentence Employer-Facing Summary

> 1. Developed an end-to-end Machine Learning Content Opportunity Scoring system evaluating 30,000 enterprise search items on a 79-million-row production dataset slice.  
> 2. Formulated client-grouped validation splits (`GroupShuffleSplit` on `client_id`) to achieve an observed **0.740 Precision@50** (a **2.18x lift** over heuristic baselines) while guarding against domain data leakage.  
> 3. Deployed a live public research paper and human-in-the-loop action playbook prioritizing editorial content refresh workflows.  
