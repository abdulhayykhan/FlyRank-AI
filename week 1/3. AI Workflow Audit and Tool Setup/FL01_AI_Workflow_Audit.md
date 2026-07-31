# FL-01 — AI Workflow Audit and Tool Setup

**Course Track:** General AI Fluency Track (Week 1 — Assignment 3)  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** July 2026  

---

## Executive Overview

This document presents the **AI Workflow Audit and Tool Setup (FL-01)**. Building on Ethan Mollick's *On-Boarding Your AI Intern* framework and Anthropic Academy's *AI Fluency: Framework & Foundations*, this audit maps 12 real weekly engineering and academic tasks into operational collaboration buckets, documents free toolkit setup, details a custom Claude Project configuration, and establishes measurable "done well" success metrics for three target tasks to be reused in FL-02 through FL-04.

---

## 1. Weekly AI Workflow Audit (12 Recurring Tasks)

Every task from my weekly workflow as a 3rd Year AI student and ML Intern is classified into one of four collaboration buckets:
- **Just Me**: Tasks requiring human accountability, ethics, empathy, or core personal vision.
- **Delegate to AI with Review**: Tasks where AI drafts initial assets, followed by human review and refinement.
- **Collaborate with AI**: Interactive, multi-turn brainstorming, debugging, or analytical synthesis.
- **Fully Automate**: Rule-based, repetitive structural operations requiring zero human intervention.

### Workflow Classification Table

| # | Task Description | Collaboration Bucket | Rationale / Boundary |
|---|---|---|---|
| **1** | **Debugging Python syntax & runtime tracebacks** in ML notebooks. | `Collaborate with AI` | AI rapidly pinpoint error causes and edge cases while I evaluate the underlying algorithm logic. |
| **2** | **Final sign-off & verification on model deployment code.** | `Just Me` | **HUMAN ONLY:** Production safety, ethical alignment, and ultimate deployment accountability rest entirely on human judgment. |
| **3** | **Drafting weekly internship progress updates & email digests.** | `Delegate to AI with Review` | AI generates clean bulleted drafts from raw terminal logs, which I review and polish before sending. |
| **4** | **Synthesizing complex technical research papers** (e.g. SEO decay studies). | `Collaborate with AI` | Interactive dialogue with AI clarifies mathematical formulations while I critically audit methodology bounds. |
| **5** | **Formatting markdown tables and documentation boilerplate.** | `Fully Automate` | Deterministic structural formatting follows strict rules with zero creative risk. |
| **6** | **Selecting capstone research problem statement & project scope.** | `Just Me` | **HUMAN ONLY:** Aligning personal career goals, technical passion, and capstone vision requires unassisted human direction. |
| **7** | **Generating initial unit test cases** for data transformation functions. | `Delegate to AI with Review` | AI drafts comprehensive edge cases faster, which I verify against expected data contract schemas. |
| **8** | **Designing data contract schemas & feature leakage boundaries.** | `Collaborate with AI` | Brainstorming potential target leakage risks with AI refines my data architecture before implementation. |
| **9** | **Refactoring legacy Python scripts to PEP 8 standards.** | `Fully Automate` | Automated linters and AI formatting tools handle style cleanup flawlessly without manual overhead. |
| **10** | **High-stakes partner & stakeholder communications.** | `Just Me` | **HUMAN ONLY:** Authentic relationship building, negotiation, and trust require human empathy and context. |
| **11** | **Writing custom SQL / Pandas data aggregation queries.** | `Collaborate with AI` | AI assists with complex query syntax while I inspect row-level grain and business rules. |
| **12** | **Creating social media summaries & short cuts** from research write-ups. | `Delegate to AI with Review` | AI distills long reports into audience-tailored snippets that I edit for tone and public safety. |

---

## 2. Toolkit & Anthropic Academy Setup

### Tool Accounts Configured:
- **Claude (Anthropic)**: Configured free account; set up dedicated Claude Project workspace.
- **ChatGPT (OpenAI)**: Active account for cross-model comparative prompting.
- **Anthropic Academy**: Enrolled in ***AI Fluency: Framework & Foundations***.

### Academy Progress Evidence:
- **Course**: *AI Fluency: Framework & Foundations* (Anthropic Academy)
- **Status**: Enrolled & Completed Module 1 (*Collaborating with AI: Effective, Efficient, Ethical & Safe*).
- **Core Key Learning**: AI is an intern, not an oracle. Effective delegation requires explicit task framing, strict context scoping, and human-in-the-loop validation.

---

## 3. Claude Project Configuration

Created a dedicated Claude Project for FlyRank AI Internship workflows with custom instructions:

```text
=== CLAUDE PROJECT CUSTOM INSTRUCTIONS ===

Role & Identity:
You are assisting Abdul Hayy Khan, a Senior 3rd Year Artificial Intelligence Student at DUET and Machine Learning Engineering Intern at FlyRank AI.

Communication Style & Tone:
- Tone: Technical, direct, concise, and rigorous.
- Formatting: Clean GitHub-Flavored Markdown (GFM) with bold highlights and structured tables.
- No Fluff: Skip polite preamble or generic pleasantries. Jump straight to the core solution or analysis.
- Language: Public-safe decision-support language (use: observed, measured, directional, decision-support; avoid: guarantees, causes, proves).

Current Focus & Goals:
- Building an 8-week Search Intelligence & Content Opportunity Scoring capstone.
- Writing robust data contracts, client-grouped validation splits (GroupShuffleSplit), and transparent baseline models.
- Mastering AI Fluency delegation frameworks (Ethan Mollick model).
```

---

## 4. Three Target Tasks & "Done Well" Success Definitions

I have selected three audit tasks to reuse across assignments **FL-02** through **FL-04**:

### Target Task 1 (FL-02 Target): *Drafting Weekly Technical Summaries & Email Digests*
- **Description**: Converting raw terminal logs, git commit messages, and notebook outputs into executive progress updates.
- **"Done Well" Success Definition (Measurable)**:
  - ⏱️ **Efficiency**: Draft generated in < 3 minutes.
  - 🎯 **Accuracy**: 100% factual alignment with git logs (zero hallucinated metrics).
  - 🧼 **Tone**: Zero generic AI fluff or buzzwords; formatted in clean GFM bullet points.
  - ⚡ **Edit Time**: Ready to send with < 60 seconds of manual editing.

### Target Task 2 (FL-03 Target): *Synthesizing & Auditing Complex Research Methodology*
- **Description**: Reading technical research papers (e.g. FlyRank SEO studies) and auditing methodology claims.
- **"Done Well" Success Definition (Measurable)**:
  - 🔍 **Methodology Rigor**: Identifies at least 2 concrete methodology questions regarding label origins or split design.
  - 🛡️ **Leakage Awareness**: Flags potential target leakage or domain authority memorization risks.
  - ⚖️ **Claim Language**: Rewrites over-claiming statements using careful decision-support words (*observed*, *directional lift*).
  - 🤝 **Tone**: Constructive, peer-review style critique.

### Target Task 3 (FL-04 Target): *Generating & Validating Data Pipeline Unit Tests*
- **Description**: Creating pytest/unittest suites for custom Pandas data transformation functions.
- **"Done Well" Success Definition (Measurable)**:
  - 🧪 **Coverage**: 100% boundary coverage of data transformation functions.
  - 🛑 **Edge Cases**: Explicit tests for null values, inf values, and empty dataframes.
  - ✅ **Pass Rate**: 0 failing assertions on valid schemas.
  - 🧹 **Code Quality**: Passes PEP 8 linter with zero warnings or redundant boilerplate.

---

## 5. Self-Check & Verification

- [x] 12 genuine, specific weekly tasks listed and classified in table format.
- [x] One line of rationale provided for every task.
- [x] At least 3 tasks honestly marked `Just Me` with human-accountability rationales.
- [x] Tool accounts and Anthropic Academy enrollment documented.
- [x] Claude Project custom instructions configured.
- [x] Three target tasks defined with specific, measurable "Done Well" criteria for FL-02 to FL-04.
