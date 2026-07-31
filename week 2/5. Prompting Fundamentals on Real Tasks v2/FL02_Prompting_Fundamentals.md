# FL-02 — Prompting Fundamentals on Real Tasks v2

**Course Track:** General AI Fluency Track (Week 2 — Assignment 5)  
**Assignment Code:** FL-02  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** July 2026  

---

## Executive Overview

This document presents **Prompting Fundamentals on Real Tasks v2 (FL-02)**. Practicing prompt engineering techniques on real production tasks rather than toy examples bridges the gap between lazy prompting and engineered AI interaction. Taking **Target Task 1 from my FL-01 audit** (*Drafting Weekly Technical Summaries & Email Progress Digests*), this document records 6 prompt iterations applying 5 core Anthropic techniques, presents an empirical cross-model evaluation between **Claude 3.5 Sonnet** and **ChatGPT (GPT-4o)**, and publishes a reusable prompt template.

---

## 1. Target Task Selection (From FL-01 Audit)

- **Selected Task**: *Drafting Weekly Technical Progress Updates & Email Summaries from Raw Git/Notebook Logs*.
- **Target Audience**: Senior ML Engineering Leads & Project Stakeholders.
- **Goal**: Convert unformatted git commits, notebook benchmark receipts, and terminal outputs into an executive-ready progress digest.

---

## 2. The 6-Step Prompt Engineering Iteration Log

```text
+---------------------------------------------------------------------------------------+
| VERSION 5 (+ Step Decomposition / Chain-of-Thought): 4-Step Analytical Execution      |
+---------------------------------------------------------------------------------------+
                                           ^
                                           |
+---------------------------------------------------------------------------------------+
| VERSION 4 (+ Specified Output Structure): Mandatory GFM Table Layout & Section Blocks |
+---------------------------------------------------------------------------------------+
                                           ^
                                           |
+---------------------------------------------------------------------------------------+
| VERSION 3 (+ Few-Shot Examples): Provided 1 Gold Standard Executive Digest Example    |
+---------------------------------------------------------------------------------------+
                                           ^
                                           |
+---------------------------------------------------------------------------------------+
| VERSION 2 (+ Context and Motivation): Added 79M-row scale & stakeholder visibility context|
+---------------------------------------------------------------------------------------+
                                           ^
                                           |
+---------------------------------------------------------------------------------------+
| VERSION 1 (+ Role Assignment): Assigned Technical Chief of Staff Persona             |
+---------------------------------------------------------------------------------------+
                                           ^
                                           |
+---------------------------------------------------------------------------------------+
| NAIVE BASELINE (VERSION 0): "Write an email update summarizing my ML work this week."  |
+---------------------------------------------------------------------------------------+
```

---

### ❌ Naive Baseline (Version 0)

**Prompt Text:**
> *"Write an email update summarizing my machine learning work this week."*

**Output Excerpt:**
> *"Subject: Weekly Machine Learning Update  
> Hi Team,  
> Hope you're having a great week! Here is a summary of what I worked on:  
> - Worked on machine learning models and data analysis.  
> - Improved model performance and checked for data issues.  
> - Built documentation and prepared research paper updates.  
> Let me know if you have any questions!  
> Best regards,  
> Abdul Hayy"*

**Iteration Note:**
- **Technique Applied**: Baseline (Lazy Naive Prompt).
- **Observed Output Behavior**: Produced a generic, high-level email template with zero specific metrics, dataset details, or technical depth. Completely useless for an ML engineering lead.

---

### 🟢 Version 1: Add Role Assignment

**Prompt Text:**
> *"Act as a Technical Chief of Staff to a Senior ML Engineering Manager. Write an email update summarizing my machine learning work this week based on these raw notes: [Completed Random Forest model on 79M rows, GroupShuffleSplit on client_id, Precision@50 = 0.740 vs 0.340 baseline, deployed 3D web paper]."**

**Output Excerpt:**
> *"Subject: Technical Progress Report: Content Opportunity Scoring Model  
> Hi Engineering Team,  
> Below is this week's technical update on the Search Intelligence Capstone:  
> Key Accomplishment: Evaluated Random Forest classifier on 79M-row dataset slice. Implemented GroupShuffleSplit on client_id to prevent domain leakage. Achieved 0.740 Precision@50 (2.18x lift over baseline). Deployed interactive 3D web paper."*

**Iteration Note:**
- **Technique Applied**: **Role Assignment** (*Technical Chief of Staff*).
- **Observed Output Difference**: Output immediately dropped conversational pleasantries; adopted a sharp engineering progress reporting style and correctly incorporated technical terms.

---

### 🟢 Version 2: Add Context and Motivation

**Prompt Text:**
> *"Act as a Technical Chief of Staff to a Senior ML Engineering Manager. **Context: We are completing Week 8 of an enterprise Search Intelligence capstone evaluating 79M+ search records. Motivation: Executive stakeholders need rapid visibility into model validation gains and production safety boundaries without reading hundreds of lines of notebook code.** Summarize these raw notes: [Completed Random Forest model, GroupShuffleSplit on client_id, Precision@50 = 0.740 vs 0.340 baseline, 0% target leakage, deployed 3D web paper]."*

**Output Excerpt:**
> *"Subject: Executive Briefing: Search Intelligence Model Validation & Deployment  
> Stakeholder Summary:  
> To address enterprise content decay without wasting editorial budgets, we finalized validation for Lane 2.  
> 1. Validation Rigor: GroupShuffleSplit on client_id prevented domain authority memorization (+8.0% bias eliminated).  
> 2. Model Performance: Random Forest reached 0.740 Precision@50 vs 0.340 Heuristic Baseline (2.18x lift).  
> 3. Production Safety: Excluded target-derived fields (trend_pct) to ensure zero target leakage."*

**Iteration Note:**
- **Technique Applied**: **Context & Motivation** (79M-row scale & stakeholder decision-visibility).
- **Observed Output Difference**: The AI framed the technical metrics around business value (preventing editorial budget waste) and explicitly highlighted leakage prevention as a safety win.

---

### 🟢 Version 3: Add Few-Shot Examples

**Prompt Text:**
> *"Act as a Technical Chief of Staff. Context: Enterprise Search Intelligence Capstone. Motivation: Stakeholder progress visibility. **Here is an example of what good output looks like:**  
> `[EXAMPLE]`  
> **Headline:** 🚀 Random Forest Reaches 0.740 Precision@50 (2.18x Baseline Lift)  
> **Key Metric:** Random Forest (0.740) vs Baseline Rule (0.340)  
> **Safety:** GroupShuffleSplit on client_id (0% Leakage)  
> `[/EXAMPLE]`  
> Now format these notes following the exact structure of the example: [Random Forest, 79M rows, GroupShuffleSplit, Precision@50 = 0.740, 0.340 baseline, 3D paper live]."*

**Output Excerpt:**
> *"🚀 **Headline:** Search Intelligence Model Finalized: 0.740 Precision@50 (2.18x Baseline Lift)  
> 📊 **Key Metric:** Random Forest (0.740 Precision@50) vs Heuristic Rule (0.340)  
> 🛡️ **Safety:** `GroupShuffleSplit` on `client_id` (0% Target Leakage, +8.0% domain bias eliminated)  
> 🌐 **Deployment:** Live 3D Research Paper deployed to GitHub Pages."*

**Iteration Note:**
- **Technique Applied**: **Few-Shot Examples** (1 Gold Standard Executive Example).
- **Observed Output Difference**: Output matched the exact syntax, emoji anchors, and tight bullet structure of the provided example. Eliminated all remaining narrative prose.

---

### 🟢 Version 4: Add Specified Output Structure

**Prompt Text:**
> *"Act as a Technical Chief of Staff. Context & Motivation: Search Intelligence progress update. Follow the few-shot structure. **Mandatory Output Structure: (1) Executive Headline, (2) Benchmark Comparison Table in GitHub-Flavored Markdown, (3) Safety & Leakage Audit Callout, (4) Next Steps.** Summarize: [Random Forest 0.740, Baseline 0.340, LR 0.400, DT 0.540, 79M rows, GroupShuffleSplit, 3D paper live]."*

**Output Excerpt:**
> *"### 🚀 Executive Headline
> Random Forest Classifier achieves **0.740 Precision@50** (2.18x directional lift over heuristic baselines) on held-out client domains.
> 
> ### 📊 Benchmark Comparison Table
> | Model / Strategy | Precision@20 | Precision@50 | ROC-AUC | Status |
> |---|---|---|---|---|
> | Baseline Rule | 0.350 | 0.340 | 0.627 | Evaluated |
> | Logistic Regression | 0.400 | 0.400 | 0.700 | Evaluated |
> | Decision Tree (d=3) | 0.650 | 0.540 | 0.742 | Evaluated |
> | **Random Forest (n=100)** | **0.750** | **0.740** | **0.750** | 🏆 **Selected** |
> 
> ### 🛡️ Safety & Leakage Audit
> - **Split Strategy:** `GroupShuffleSplit` on `client_id` (0% domain data leakage).
> - **Feature Exclusions:** `trend_pct` strictly excluded."*

**Iteration Note:**
- **Technique Applied**: **Specified Output Structure** (Mandatory GFM Table Layout & Blocks).
- **Observed Output Difference**: Output transformed into a clean markdown document featuring a complete benchmark comparison table across all 4 evaluated model strategies.

---

### 🏆 Version 5: Add Step Decomposition / Chain-of-Thought (Final Prompt)

**Prompt Text:**
> *"Act as a Technical Chief of Staff to an ML Manager. Context: Enterprise Search Intelligence update. Follow the mandatory structure (Headline, GFM Benchmark Table, Safety Audit, Next Steps). **Execute via 4 explicit steps: Step 1: Extract raw quantitative metrics and filter out minor commits. Step 2: Calculate directional lift over baseline. Step 3: Audit split design for leakage risks. Step 4: Assemble final report.** Notes: [Random Forest 0.740, Baseline 0.340, 79M rows, GroupShuffleSplit on client_id, trend_pct excluded, live paper deployed]."*

**Output Excerpt:**
> *"### 1. Directional Lift Calculation
> - Baseline Precision@50: 0.340
> - Random Forest Precision@50: 0.740
> - Calculated Lift: 0.740 / 0.340 = **2.18x Directional Lift**
> 
> ### 2. Executive Headline
> Final model validation complete: Random Forest delivers **2.18x directional lift** over heuristic baselines on held-out enterprise client domains.
> 
> ### 3. Benchmark Metrics
> | Model Strategy | Precision@50 | ROC-AUC | Directional Lift |
> |---|---|---|---|
> | Baseline Heuristic Rule | 0.340 | 0.627 | 1.00x |
> | **Random Forest (Selected)** | **0.740** | **0.750** | **2.18x** |
> 
> ### 4. Validation & Leakage Audit
> - **Domain Leakage:** `GroupShuffleSplit` on `client_id` ensures unseen client evaluation.
> - **Target Leakage:** `trend_pct` strictly excluded."*

**Iteration Note:**
- **Technique Applied**: **Step Decomposition / Chain-of-Thought** (4-Step Analytical Process).
- **Observed Output Difference**: AI explicitly calculated the exact ratio (2.18x) before outputting text, eliminating mental math errors and ensuring 100% metric consistency across all sections.

---

## 3. Empirical Cross-Model Comparison (Claude 3.5 Sonnet vs ChatGPT GPT-4o)

The final engineered prompt (Version 5) was executed on both **Claude 3.5 Sonnet** and **ChatGPT (GPT-4o)** using the exact same input context. Below is the honest comparative analysis:

| Evaluation Dimension | Claude 3.5 Sonnet Output | ChatGPT (GPT-4o) Output | Comparative Winner |
|---|---|---|---|
| **Tone & Style** | Direct, concise, technical GFM. Jumped immediately to Step 1 with zero preamble. | Enthusiastic, conversational. Added intro text (*"Here is your executive summary digest..."*). | 🏆 **Claude** (Zero fluff) |
| **Formatting Adherence** | Followed GFM table syntax perfectly with clean column padding. | Generated tables correctly, but excessively bolded every single table header and bullet item. | 🏆 **Claude** (Clean GFM) |
| **Mathematical Accuracy** | Executed 2.18x lift calculation accurately in Step 1. | Executed 2.18x lift calculation accurately. | 🤝 **Tie** |
| **Constraint Obedience** | Respected negative constraints and step ordering flawlessly. | Attempted to add polite sign-off text at the end despite strict formatting rules. | 🏆 **Claude** (Strict compliance) |
| **Failure Points Observed** | Slightly truncated long code block padding on narrow screens. | Included unnecessary conversational wrapping text before and after markdown tables. | 🏆 **Claude** |

---

## 4. Final Reusable Prompt Template (Copy-Paste Ready)

```text
========================================================================================
REUSABLE TEMPLATE: EXECUTIVE TECHNICAL PROGRESS DIGEST GENERATOR
========================================================================================

Role & Persona:
Act as a Technical Chief of Staff to a Senior Engineering Lead.

Context & Motivation:
Context: Weekly progress report for a technical project.
Motivation: Provide executive leadership with immediate quantitative visibility into progress, metric gains, and risk controls without drowning them in raw code or unformatted logs.

Step Decomposition (Execute in Order):
1. Extract raw quantitative metrics and filter out non-essential operational logs.
2. Calculate relative lift or percentage change over baseline benchmarks.
3. Audit data integrity, validation split design, and safety risks.
4. Assemble output following the mandatory structure below.

Mandatory Output Structure:
1. Executive Headline (1 sentence stating headline quantitative gain).
2. Benchmark Comparison Table (GFM Table: Model/Strategy, Primary Metric, Baseline Lift, Status).
3. Risk & Safety Audit Callout (Validation split method, data leakage checks).
4. Next Steps & Action Items (3 bullet points).

Negative Constraints:
- Skip polite preambles ("Here is your update") or generic conversational sign-offs.
- Jump directly into Section 1. Do not use generic buzzwords ("results-oriented", "cutting-edge").
========================================================================================
```

---

## 5. Verification Checklist (Pass / Revise Self-Audit)

- [x] **5+ iterations beyond naive version**: Baseline (V0) plus 5 distinct single-technique versions.
- [x] **Named techniques applied**: Role Assignment, Context & Motivation, Few-Shot Examples, Output Structure, Step Decomposition.
- [x] **Output-focused notes**: Notes explain observed output differences (e.g. math calculation accuracy, table structure), not just prompt text.
- [x] **Cross-model comparison specific**: Detailed side-by-side evaluation between Claude and ChatGPT.
- [x] **Final template reusable**: Standalone template ready for any stranger or project context.
- [x] **Real task used**: Built directly on Target Task 1 from FL-01 audit.
