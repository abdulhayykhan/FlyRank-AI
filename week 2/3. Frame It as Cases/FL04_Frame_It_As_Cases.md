# Frame It as Cases: Work That Speaks for Itself

**Course Track:** General AI Fluency Track (Week 2 — Assignment 3)  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** July 2026  

---

## 🎙️ Voice Card (Standing Instruction)

> **"Direct, empirical, plain, technical, zero fluff."**

*(Note: Added as a standing voice card instruction in my Claude Project to ensure all generated drafts reflect my actual speaking voice—eliminating generic marketing jargon).*

---

## 1. Interactive Interview (Raw, Messy & Honest Answers)

Below is the one-question-at-a-time audit interview conducted with my AI Tutor to extract real engineering decisions and unpolished facts before framing:

```text
=== RAW ENGINEERING INTERVIEW DIALOGUE ===

AI TUTOR: "Question 1: What is the core problem enterprise SEO teams actually face with decaying content, and why do traditional rules fail?"

ABDUL HAYY: "Enterprise publications manage tens of thousands of URLs. When search traffic drops, teams rely on naive rules like 'rewrite any page older than 180 days'. In our 79M-row dataset analysis, we found that 48% of stale pages are actually still growing in traffic! Static rules fail because age alone doesn't mean a page is dying—wasting thousands of dollars on unnecessary editorial rewrites."

AI TUTOR: "Question 2: What key engineering decisions did you make when setting up data contracts and validation splits?"

ABDUL HAYY: "First, I enforced a strict 90-day observation window contract where 1 row = 1 content item. Second, I excluded 'trend_pct' from feature inputs because it caused 100% target label leakage. Third, instead of a random train-test split, I used GroupShuffleSplit on client_id. Random splits allow pages from the same domain into both sets, letting models memorize client baselines rather than learning real signals—artificially inflating Precision by over 8%."

AI TUTOR: "Question 3: What exact quantitative outcome did your model achieve, and how did you turn predictions into editorial action?"

ABDUL HAYY: "Our Random Forest model achieved a 0.740 Precision@50 on unseen client domains compared to 0.340 for the heuristic baseline—a 2.18x directional lift. Out of the top 50 flagged pages, 37 are true declining pages. I translated model probabilities into an Archetype Action Engine with strict No-Go rules: no automated LLM text publishing and no automated 301 redirects."
```

---

## 2. Framed Case Study (The Three Beats)

### Case Study Title: Search Intelligence & Content Opportunity Scoring
**Target Reader:** ML Engineering Hiring Manager / Lead Data Scientist  
**Primary Action:** Schedule a 15-minute technical interview / inspect live research paper.  

```text
+---------------------------------------------------------------------------------------+
| BEAT 1: THE PROBLEM                                                                   |
+---------------------------------------------------------------------------------------+
Enterprise digital publications manage portfolios with tens of thousands of indexable
URLs. Over time, search intent shifts and algorithm layouts evolve, causing high-volume
content to decay. Traditional quarterly audits rely on naive threshold rules (flagging
any page older than 180 days), producing high false-positive rates. Our empirical analysis
revealed that 48% of stale content items are still growing in organic traffic—proving that
static age rules waste significant editorial budgets on non-declining pages.

+---------------------------------------------------------------------------------------+
| BEAT 2: WHAT I DID & DECIDED                                                          |
+---------------------------------------------------------------------------------------+
Evaluating a 79-million-row production dataset slice (30,000 enterprise content items),
I formulated a binary classification and priority scoring framework.
Key Engineering Decisions:
- Data Contract: Aggregated 90-day feature window where 1 row = 1 content item.
- Target Leakage Control: Completely excluded `trend_pct` and `trend_direction` from inputs.
- Client-Grouped Holdout Split: Implemented `GroupShuffleSplit` on `client_id` (80% train /
  20% test holdout). This prevented models from memorizing domain authority baselines,
  eliminating a +8.0% overestimation bias seen in naive random splits.
- Model Training: Evaluated Baseline Heuristics, Logistic Regression, Decision Trees, and
  Random Forest Classifiers.

+---------------------------------------------------------------------------------------+
| BEAT 3: WHAT CAME OF IT                                                               |
+---------------------------------------------------------------------------------------+
- Quantitative Performance: Random Forest achieved an observed 0.740 Precision@50 and a
  0.750 ROC-AUC on held-out client domains—delivering a 2.18x directional lift over the
  0.340 heuristic baseline rule.
- Content Action Playbook: Translated raw probabilities into an Archetype Action Engine
  mapping model scores to specific editorial workflows (Full Refresh, Title/Meta Rewrite).
- Human-in-the-Loop Safeguards: Enforced strict No-Go rules prohibiting unassisted LLM
  writing and automated 301 redirects.
- Shipped Research Paper: Assembled and deployed an open-source 3D-animated web paper at
  https://abdulhayykhan.github.io/FlyRank-AI/.
```

---

## 3. Author Bio & Conversion CTA Copy

### Author Bio Copy:
> **Abdul Hayy Khan** is a 3rd Year Artificial Intelligence Student at Dawood University of Engineering & Technology (DUET) and a Machine Learning Engineering Intern at FlyRank AI. He specializes in building leak-free machine learning decision-support systems and production search intelligence pipelines.

### Conversion Call to Action (CTA):
> **"Ready to discuss machine learning priority scoring or inspect my production capstone codebase?"**  
> 👉 **[Schedule a 15-Minute Technical Interview]** | **[Explore Live 3D Capstone Paper]** | **[GitHub Repository]**

---

## 4. Before & After Comparison (Generic AI vs Edited Voice)

To prove the voice card eliminated generic AI fluff, here is a direct before-and-after line audit:

### ❌ BEFORE (Generic AI Copy):
> *"I am a passion-driven and results-oriented Machine Learning Engineer leveraging state-of-the-art AI frameworks and cutting-edge data science methodologies to unlock transformative business growth, optimize search performance, and deliver robust end-to-end data solutions."*  
*(Why it fails: 34 words of pure buzzwords—'passion-driven', 'results-oriented', 'state-of-the-art', 'transformative growth'—without stating a single real metric or specific skill).*

### ✅ AFTER (My Edited Voice Line):
> *"I build leak-free machine learning decision-support systems that score enterprise content decay on production search data, achieving an observed 0.740 Precision@50 (a 2.18x lift over baseline rules) on client holdout domains."*  
*(Why it works: 29 words of direct, empirical, plain facts containing my exact model, dataset size, split method, and verified metric).*

---

## 5. Verification Checklist (Pass / Revise Self-Audit)

- [x] **Voice card defined**: "Direct, empirical, plain, technical, zero fluff" (5 words).
- [x] **Raw interview recorded**: Captured messy human answers to 3 core engineering questions.
- [x] **Three beats present**: The Problem, What I Did & Decided, What Came of It.
- [x] **Author Bio & CTA present**: Points directly to scheduling a 15-minute technical interview.
- [x] **Before/After comparison**: Demonstrates elimination of generic AI marketing fluff.
