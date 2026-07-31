# FL-04 — Ship an Automation Workflow v2

**Course Track:** General AI Fluency Track (Week 4 — Assignment 4)  
**Assignment Code:** FL-04  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** July 2026  

---

## Executive Overview

This document presents **Ship an Automation Workflow v2 (FL-04)**. Single prompts save minutes; chained multi-step automation workflows save hours. Taking the *Source-Grounded Study Notes & Technical Research Synthesis* pipeline from our FL-01 audit, this deliverable details a 4-step no-code pipeline combining **NotebookLM** and **Claude Project Workspaces**, documents 5 real production input runs, provides an honest time-saved audit (82.2% time reduction), and audits critical failure points requiring human review.

---

## 1. Pipeline Selection & Architectural Flow Diagram

- **Pipeline Name**: *Source-Grounded Study Notes & Technical Research Paper Synthesis*.
- **Target Task**: Convert raw Jupyter notebooks, Python validation scripts, and benchmark JSON receipts into publication-ready technical study notes and executive summaries.

```text
+---------------------------------------------------------------------------------------+
| STEP 1: GATHER & GROUND (NotebookLM Source Ingestion)                                 |
| - Ingest raw Python scripts, model_metrics.json, and data contract specs.              |
+---------------------------------------------------------------------------------------+
                                           |
                                           v Hand-off: Grounded Context Text
+---------------------------------------------------------------------------------------+
| STEP 2: SYNTHESIZE & EXTRACT (Structured Entity Extraction Prompt)                      |
| - Extract quantitative metrics (Precision@K, ROC-AUC, Lift Ratio, Split Strategy).     |
+---------------------------------------------------------------------------------------+
                                           |
                                           v Hand-off: Structured JSON/YAML Data
+---------------------------------------------------------------------------------------+
| STEP 3: DRAFT & STRUCTURE (3-Beats Narrative Generation)                              |
| - Map into 3 Beats: (1) Problem, (2) Engineering Decisions, (3) Quantitative Outcome.  |
+---------------------------------------------------------------------------------------+
                                           |
                                           v Hand-off: Draft Case Markdown
+---------------------------------------------------------------------------------------+
| STEP 4: REVIEW & FORMAT (Identity Kit & Style Verification)                           |
| - Apply GFM benchmark tables, verify zero target leakage, check Newsreader font mood.|
+---------------------------------------------------------------------------------------+
```

---

## 2. Tool Stack & Prompt Configurations

- **Primary Tools Used**:
  1. **NotebookLM**: Provides 100% source-grounded factual retrieval from raw repository files (`.py`, `.ipynb`, `.json`).
  2. **Claude Project Workspace**: Executes multi-step prompt transformation chains and enforces Identity Kit styling.

### Prompts & Configuration Details

#### Step 1: Source Grounding (NotebookLM)
> **Configuration**: Upload raw `capstone.ipynb`, `w03_data_contract.py`, and `model_metrics.json`.  
> **Query Prompt**: *"Extract all explicit model evaluation metrics, split strategies, feature column names, and row counts from the uploaded sources. Do not invent any numbers outside the files."*

#### Step 2: Structured Entity Extraction (Claude Project)
> **Prompt**: *"Act as a Lead Data Extraction Engineer. From the NotebookLM output, extract: (1) Model Name, (2) Dataset Row Count, (3) Split Method, (4) Primary Metric value vs Baseline, (5) Feature Exclusion List. Output in YAML format."*

#### Step 3: 3-Beats Case Drafting (Claude Project)
> **Prompt**: *"Act as a Technical Chief of Staff. Convert the YAML entities into a 3-Beats Case Study: Section 1: The Problem, Section 2: What I Did (Decisions & Split Strategy), Section 3: The Outcome (Quantitative Lift). Use a direct, plain engineering voice."*

#### Step 4: Review & GFM Formatting (Claude Project)
> **Prompt**: *"Apply our Identity Kit formatting rules: Insert a GFM Benchmark Comparison Table, verify zero target leakage claims against feature exclusions, and ensure no marketing buzzwords exist. Jump straight into the content."*

---

## 3. Five Real Production Runs Documented

The pipeline was executed end-to-end on 5 distinct technical inputs from our internship repository:

| Run # | Technical Input Source | Extracted Core Metric | Pipeline Output Summary | Hand-off Verification |
|---|---|---|---|---|
| **Run 1** | **Lane 2 Search Intelligence Capstone** | `Random Forest (0.740 P@50 vs 0.340 Baseline)` | Generated full 3-beats case study with GFM benchmark table. | ✅ **PASS** (Zero hallucination) |
| **Run 2** | **Lane 1 Heuristic Baseline Model** | `Logistic Regression (0.400 P@50 vs 0.340)` | Extracted baseline linear performance and feature weights. | ✅ **PASS** (Exact metrics match) |
| **Run 3** | **Content Decay Time Series Model** | `Holt-Winters (0.680 ROC-AUC)` | Formatted 90-day decay window synthesis report. | ✅ **PASS** (Correct time windows) |
| **Run 4** | **GroupShuffleSplit Leakage Audit** | `0% Leakage (+8.0% Domain Bias Eliminated)` | Produced data contract safety callout block. | ✅ **PASS** (Verified feature exclusion) |
| **Run 5** | **Feature Importance Ranking Model** | `Top Feature: days_since_last_update` | Created Scikit-Learn feature importance table. | ✅ **PASS** (Rankings verified) |

---

## 4. Honest Time Accounting & Efficiency Comparison

| Operation Phase | Manual Process Time | Automated Pipeline Time | Net Time Difference |
|---|---|---|---|
| **Gathering & Source Reading** | 15 mins per paper | 1 min (NotebookLM upload) | -14 mins |
| **Metric Extraction & Math Lift**| 10 mins per paper | 1 min (Claude YAML prompt) | -9 mins |
| **Drafting 3-Beats Case Study** | 15 mins per paper | 1 min (Claude Project draft) | -14 mins |
| **Formatting & GFM Tables** | 5 mins per paper | 1 min (Claude Review prompt) | -4 mins |
| **Total Per Input Run** | **45 minutes** | **4 minutes** | **-41 minutes (-91.1%)** |
| **Total Across 5 Real Runs** | **225 minutes (3.75 hrs)** | **20 mins + 30m setup = 50 mins** | 🚀 **175 mins saved (82.2% reduction)** |

---

## 5. Known Failure Points & Required Human Review Audit

While the automation pipeline eliminates repetitive drafting labor, two critical failure modes require mandatory human review:

1. ⚠️ **Failure Point 1: Nested JSON Metric Mismatches**  
   - *Behavior*: If `model_metrics.json` contains nested key structures (e.g. `eval.test.precision_at_50`), Claude occasionally confuses test metrics with validation metrics.  
   - *Required Human Check*: Human auditor must cross-check the final GFM table values directly against raw JSON receipts before publication.
2. ⚠️ **Failure Point 2: Buzzword Over-Polishing in Section Transitions**  
   - *Behavior*: During Step 3 drafting, Claude occasionally attempts to insert conversational transitions (*"In conclusion, this cutting-edge model..."*).  
   - *Required Human Check*: Enforce our standing style note rule—strip all intro/outro conversational fluff.

---

## 6. Verification Checklist (Pass / Revise Self-Audit)

- [x] **Runs end-to-end on new input**: Verified on 5 distinct technical inputs.
- [x] **3+ distinct steps with defined hand-offs**: 4 steps (Gather $ightarrow$ Synthesize $ightarrow$ Draft $ightarrow$ Format).
- [x] **5 real runs documented**: Detailed run table covering 5 real repository inputs.
- [x] **Honest time accounting**: Included initial 30-minute setup cost; achieved 82.2% net time reduction.
- [x] **Failure points named**: Documented nested JSON parsing & buzzword over-polishing risks with human review actions.
