# The Prompt Ladder: Systematic Prompt Engineering Audit

**Course Track:** General AI Fluency Track (Week 2 — Assignment 4)  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** July 2026  

---

## Executive Overview

This document presents **The Prompt Ladder (Week 2 Assignment 4)**. Changing multiple variables at once in a prompt hides what actually drives model performance. To systematically master prompt engineering, this assignment constructs a 6-step prompt ladder starting from a weak baseline and adding **exactly one named layer per version**, evaluating side-by-side behavioral output changes, recording an honest prompt failure moment, and publishing a clean reusable template.

---

## 🪜 The 6-Step Prompt Ladder Overview

```text
+---------------------------------------------------------------------------------------+
| VERSION 5: + Specified Output Format & Verification Criteria (Final Production Prompt) |
+---------------------------------------------------------------------------------------+
                                           ^
                                           |
+---------------------------------------------------------------------------------------+
| VERSION 4: + Negative Constraints & Boundaries (Honest Failure / Over-Constraint Test)|
+---------------------------------------------------------------------------------------+
                                           ^
                                           |
+---------------------------------------------------------------------------------------+
| VERSION 3: + Real Production Context & Dataset Specs (79M rows, GroupShuffleSplit)   |
+---------------------------------------------------------------------------------------+
                                           ^
                                           |
+---------------------------------------------------------------------------------------+
| VERSION 2: + Defined Role & Audience Persona (Senior ML Auditor -> Hiring Manager)    |
+---------------------------------------------------------------------------------------+
                                           ^
                                           |
+---------------------------------------------------------------------------------------+
| VERSION 1: + Clear Specific Goal (Audit content decay model feature leakage)           |
+---------------------------------------------------------------------------------------+
                                           ^
                                           |
+---------------------------------------------------------------------------------------+
| BASELINE (VERSION 0): Weak Generic Prompt ("Help me check my ML search model...")     |
+---------------------------------------------------------------------------------------+
```

---

## 1. Step-by-Step Prompt Ladder Evaluation

### ❌ Baseline (Version 0): Weak Prompt

**Prompt Text:**
> *"Help me check my machine learning search model for data leakage and write a summary."*

**Output Excerpt:**
> *"Data leakage occurs when information from outside the training dataset is used to create the model. Here are three common types of data leakage: 1. Target Leakage (when predictor variables include the target), 2. Train-Test Contamination (when test data leaks into training). You can fix this in Python using `train_test_split(X, y, test_size=0.2)` from Scikit-Learn."*

**Notes:**
- **What Changed**: Baseline (un-engineered prompt).
- **What Improved**: N/A (generic textbook response).
- **What Failed**: Gives a 101-level lecture on machine learning concepts; fails to address domain authority leakage across client websites, feature observation windows, or enterprise datasets.
- **What to Try Next**: Add a clear, specific goal to focus the task.

---

### 🟢 Version 1: Add Layer 1 — Clear Specific Goal

**Prompt Text:**
> *"Help me check my machine learning search model for data leakage and write a summary. **Goal: Audit feature leakage and validation split design for predicting enterprise organic search content decay.**"*

**Output Excerpt:**
> *"To audit feature leakage in an organic search content decay model, focus on feature timing. Ensure features like `days_since_last_update`, `avg_position`, and `impressions_90d` are measured strictly prior to the decay evaluation moment. If your feature set includes post-decay metrics, your model will suffer from target leakage."*

**Notes:**
- **What Changed**: Added Layer 1 (**Clear Goal / Specific Task**).
- **What Improved in Output**: Stopped defining generic machine learning terms; shifted focus directly to search content decay features (`avg_position`, `impressions_90d`).
- **What Failed**: Still assumed a standard random `train_test_split`, ignoring client domain authority memorization.
- **What to Try Next**: Define the auditor persona and target audience.

---

### 🟢 Version 2: Add Layer 2 — Defined Audience & Role Persona

**Prompt Text:**
> *"Act as a Senior ML Engineering Auditor reviewing work for an enterprise Search Intelligence lead. Audit feature leakage and validation split design for predicting enterprise organic search content decay."*

**Output Excerpt:**
> *"### ML Audit Review: Content Decay Model
> **Critical Concern 1: Split Strategy.** Standard random train/test splits are unacceptable for multi-tenant Search Intelligence datasets. Content items belonging to the same client domain must not span both splits.
> **Critical Concern 2: Temporal Scoping.** Verify that all impression aggregates use a strictly pre-decision trailing window."*

**Notes:**
- **What Changed**: Added Layer 2 (**Defined Role & Audience Persona**).
- **What Improved in Output**: Completely dropped conversational pleasantries; adopted a sharp, authoritative peer-review tone.
- **What Failed**: Suggested general time-series splitting because it lacked real dataset metadata (`client_id`).
- **What to Try Next**: Inject real production dataset specifications and column schemas.

---

### 🟢 Version 3: Add Layer 3 — Real Production Context & Dataset Specs

**Prompt Text:**
> *"Act as a Senior ML Engineering Auditor reviewing work for an enterprise Search Intelligence lead. Audit feature leakage and validation split design for predicting enterprise organic search content decay. **Context: Dataset is a 79M-row warehouse release slice (30,000 content items across enterprise client_id). Observation window is trailing 90 days. Validation split used is GroupShuffleSplit on client_id.**"*

**Output Excerpt:**
> *"### Code Audit: Client-Grouped Validation Design
> Using `GroupShuffleSplit` on `client_id` is the correct decision. Random splits allow models to memorize client domain authority baselines, causing a +8.0% artificial overestimation bias in Precision@50. Holding out entire client domains tests true out-of-sample generalization to unseen enterprise websites."*

**Notes:**
- **What Changed**: Added Layer 3 (**Real Production Context & Dataset Specs**).
- **What Improved in Output**: Output specifically evaluated `GroupShuffleSplit` on `client_id` and quantified domain memorization risk (+8.0% bias).
- **What Failed**: Still permitted hypothetical discussion of future trend metrics like `trend_pct`.
- **What to Try Next**: Add strict negative constraints prohibiting target-derived fields.

---

### ⚠️ Version 4: Add Layer 4 — Negative Constraints (HONEST FAILURE MOMENT!)

**Prompt Text:**
> *"Act as a Senior ML Engineering Auditor reviewing work for an enterprise Search Intelligence lead. Audit feature leakage and validation split design for predicting enterprise organic search content decay. Context: Dataset is a 79M-row warehouse release slice (30,000 content items across client_id). Observation window is trailing 90 days. Validation split used is GroupShuffleSplit on client_id. **STRICT CONSTRAINT: Do NOT mention trend_pct or trend_direction. STRICT CONSTRAINT: Limit response to under 100 words and do NOT discuss baseline rule comparisons.**"*

**Output Excerpt:**
> *"Audit Summary: Model uses GroupShuffleSplit on client_id across 30,000 rows. Feature window is 90 days. Leakage check passed. Features validated: days_since_last_update, avg_position, log_impressions_90d."*

**Notes (Honest Prompt Failure Analysis):**
- **What Changed**: Added Layer 4 (**Negative Constraints & Rigid Limits**).
- **What Improved in Output**: Successfully suppressed mentions of `trend_pct`.
- **💥 WHAT FAILED / MADE IT WORSE**: **THIS LAYER BROKE THE OUTPUT!** The under-100-word constraint made the AI output uselessly blunt and sterile. It stripped away essential technical explanations of *why* leakage occurs and suppressed vital comparisons against baseline rules.
- **What to Try Next**: Remove rigid word counts; replace with specified output formatting and verification checklists.

---

### 🏆 Version 5: Add Layer 5 — Specified Output Format & Verification Checklist (Final Prompt)

**Prompt Text:**
> *"Act as a Senior ML Engineering Auditor reviewing work for an enterprise Search Intelligence lead. Audit feature leakage and validation split design for predicting enterprise organic search content decay. Context: Dataset is a 79M-row warehouse release slice (30,000 content items across client_id). Observation window is trailing 90 days. Validation split used is GroupShuffleSplit on client_id. Exclude target-derived fields (trend_pct). **Output Format: Provide (1) Executive Audit Summary Table, (2) 9-Point Leakage Checklist Table with PASS/FAIL status, and (3) Python Verification Code Block comparing Random Forest (Precision@50 = 0.740) vs Baseline Rule (0.340).**"*

**Output Excerpt:**
> *"### 1. Executive Audit Summary
> | Metric / Design | Value / Specification | Evaluation Verdict |
> |---|---|---|
> | Dataset Scale | 79M Rows (30,000 Content Items) | Verified Production Slice |
> | Split Strategy | `GroupShuffleSplit` on `client_id` | PASS (Zero Domain Leakage) |
> | Model Performance | Precision@50 = 0.740 (vs 0.340 Baseline) | PASS (2.18x Directional Lift) |
>
> ### 2. 9-Point Leakage Checklist
> | # | Audit Check | Status | Technical Rationale |
> |---|---|---|---|
> | 1 | Pre-Decision Observation Window | PASS | Features aggregated over trailing 90-day window prior to evaluation. |
> | 2 | Target-Derived Feature Exclusion | PASS | `trend_pct` and `trend_direction` strictly excluded from inputs. |
> | 3 | Client Domain Group Holdout | PASS | `GroupShuffleSplit` prevents domain authority memorization (+8.0% bias avoided). |
>
> ```python
> # 3. Python Verification Code Block
> from sklearn.model_selection import GroupShuffleSplit
> gss = GroupShuffleSplit(n_splits=1, test_size=0.20, random_state=42)
> train_idx, test_idx = next(gss.split(X, y, groups=df['client_id']))
> assert len(set(df.iloc[train_idx]['client_id']).intersection(set(df.iloc[test_idx]['client_id']))) == 0
> print("PASS: Zero client_id domain overlap between train and test sets.")
> ```"*

**Notes:**
- **What Changed**: Added Layer 5 (**Specified Output Format & Verification Checklist**).
- **What Improved in Output**: Produced an actionable, publication-ready audit report with structured GFM tables, metric comparisons (0.740 vs 0.340), and executable assertion code.
- **What Failed**: None—achieved full production engineering audit standard.
- **What to Try Next**: Finalize as a reusable prompt template for team distribution.

---

## 2. Final Clean Reusable Prompt (Copy-Paste Ready)

```text
========================================================================================
REUSABLE PRODUCTION PROMPT: SEARCH INTELLIGENCE MODEL LEAKAGE AUDIT
========================================================================================

Role & Persona:
Act as a Senior Machine Learning Engineering Auditor reviewing predictive search systems for an enterprise Search Intelligence Lead.

Task Goal:
Audit feature leakage, temporal observation windows, and validation split designs for a machine learning content opportunity scoring system.

Context & Dataset Parameters:
- Dataset: 79M-row production search dataset slice (30,000 pseudonymized content items across client_id).
- Feature Window: Trailing 90 days prior to evaluation moment.
- Target Label: Binary classification target `is_declining_label` (Base rate = 52.2%).
- Validation Split: Client-Grouped Holdout using `GroupShuffleSplit` on `client_id` (80% train / 20% test).
- Models Evaluated: Random Forest Classifier (Precision@50 = 0.740) vs Baseline Heuristic Rule (Precision@50 = 0.340).

Negative Constraints:
- Exclude all target-derived future fields (`trend_pct`, `trend_direction`) from predictor inputs.
- Avoid vague marketing jargon; enforce empirical decision-support language (*observed*, *directional lift*).

Output Format Requirements:
1. Executive Audit Summary Table (Dataset scale, split strategy, baseline comparison).
2. 9-Point Leakage Audit Checklist Table with PASS/FAIL statuses and technical rationales.
3. Python Verification Code Block containing `GroupShuffleSplit` assertion checks.
========================================================================================
```

---

## 3. Verification Checklist (Pass / Revise Self-Audit)

- [x] **Six runs total**: Baseline (V0) plus 5 single-layer iterations.
- [x] **One layer per version**: Single named ingredient added at every step.
- [x] **Output-focused notes**: Notes describe behavioral output changes, not prompt changes.
- [x] **Honest failure moment**: Documented in Version 4 (rigid word limit broke output quality).
- [x] **Final prompt reusable**: Clean copy-paste prompt ready for any engineer on the track.
