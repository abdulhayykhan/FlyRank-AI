# Ship the Ugly One

**Course Track:** General AI Fluency Track (Week 5 — Assignment 2)  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** July 2026  

---

## Executive Overview

This document presents **Ship the Ugly One (Week 5 Assignment 2)**. A private portfolio locked on a local machine teaches nothing; getting a real URL live and into the hands of a real reader transforms the project from a someday-idea into concrete reality. This deliverable documents our fully assembled, live portfolio deployment at [`https://abdulhayykhan.github.io/FlyRank-AI/`](https://abdulhayykhan.github.io/FlyRank-AI/), records feedback from a real industry reviewer, provides a code-explanation audit ensuring zero mystery code, and outlines an honest "still ugly" list of rough edges to polish.

---

## 1. Live Deployment & Sitemap Verification

The complete portfolio shell, real case studies, and interactive visual components are live and publicly reachable across all devices:

- 🌐 **Public Live URL**: [https://abdulhayykhan.github.io/FlyRank-AI/](https://abdulhayykhan.github.io/FlyRank-AI/)
- 📦 **GitHub Repository**: [https://github.com/abdulhayykhan/FlyRank-AI](https://github.com/abdulhayykhan/FlyRank-AI)
- 📄 **Submission URL Record**: `submission/paper_url.txt`

### Assembled Portfolio Sections Verification

| Sitemap Section | Live Status | Real Content / Visual Asset Embedded |
|---|---|---|
| **1. Hero Header** | ✅ **LIVE** | One-Line Claim + 4 Stat Badges (79M Rows, 0.740 P@50, 2.18x Lift). |
| **2. Featured Case Study** | ✅ **LIVE** | Lane 2 Search Intelligence: 3 Beats (Problem, Decisions, Outcome). |
| **3. Benchmark Charts** | ✅ **LIVE** | Real Matplotlib figures (`feature_importances.png`, `precision_at_k.png`). |
| **4. Priority Calculator** | ✅ **LIVE** | Interactive Vanilla JS decay probability calculation widget. |
| **5. Author Bio & CTAs** | ✅ **LIVE** | Abdul Hayy Khan bio + 15-Minute Technical Interview Booking CTA. |

---

## 2. Real Person Reviewer Feedback & Reaction

The live URL was shared with a **Senior ML Engineering Lead** for candid, real-world review. Below is the captured reaction:

### Reviewer Profile:
- **Role**: Senior Machine Learning Engineer / Technical Lead.
- **Review Context**: Evaluated site on both desktop monitor and mobile browser.

### Captured Reactions & Feedback:
- 🟢 **What Landed Immediately**:  
  *"The `GroupShuffleSplit` on `client_id` explanation and the baseline comparison table (Random Forest 0.740 vs 0.340 Baseline Rule) immediately set this apart. It reads like a genuine technical research paper rather than a generic developer portfolio."*
- 🟡 **What Confused Them**:  
  *"On mobile viewports, the interactive Content Priority Calculator slider for `days_since_last_update` needed explicit numerical units (e.g. '120 days' vs raw '120')."*
- 💡 **Key Takeaway**:  
  *"The site proves you understand data leakage prevention and quantitative model evaluation on production-scale data."*

---

## 3. "No Mystery Code" Technical Architecture Audit

As an AI-assisted build, every line of code in the site infrastructure is fully understood and explainable:

```text
========================================================================================
                      PORTFOLIO TECHNICAL ARCHITECTURE
========================================================================================

  [ HTML5 SEMANTIC LAYOUT ]          [ CSS DESIGN TOKENS ]        [ VANILLA JS PRIORITY ENGINE ]
  <header> Hero Claim                --bg-primary: #F8FAFC        function calculateDecayScore() {
  <main>   Case Study Beats          --text-main:  #0F172A          const score = 1 / (1 + Math.exp(-z));
  <section>Interactive Calculator    --brand-blue: #2563EB          return Math.round(score * 100);
  <footer> Conversion CTA            --accent-sky: #38BDF8        }
========================================================================================
```

1. **Semantic HTML5 Structure**: Uses `<header>`, `<main>`, `<section id="case-study">`, and `<footer>` tags to guarantee 100% SEO indexability and screen-reader accessibility.
2. **Identity Kit CSS Tokens**: Custom CSS variables match our exact locked palette (`#0F172A`, `#F8FAFC`, `#2563EB`, `#38BDF8`) with responsive CSS Grid layouts.
3. **Vanilla JS Priority Engine**: The in-page calculator widget executes a client-side logistic weighting formula locally in the browser:
   $$z = -2.5 + (0.015 \cdot 	ext{days\_stale}) + (0.08 \cdot 	ext{avg\_position})$$
   $$P(	ext{Decay}) = rac{1}{1 + e^{-z}}$$

---

## 4. Honest "Still Ugly" List (Rough Edges to Polish)

Getting to live early reveals rough edges that will be polished in subsequent weeks:

1. ⚠️ **Mobile Table Overflow Styling**: On narrow iOS viewports (< 375px), the GFM benchmark table requires horizontal touch-scrolling, which lacks a custom scrollbar indicator.
2. ⚠️ **Raw Math Delimiters**: Math formulas in markdown callout blocks currently display standard LaTeX text strings rather than KaTeX script renders.
3. ⚠️ **Theme Toggle Transition**: Dark mode color switching functions correctly but lacks a smooth 300ms CSS transition animation.

---

## 5. Verification Checklist (Pass / Revise Self-Audit)

- [x] **Portfolio live & reachable**: Live at `https://abdulhayykhan.github.io/FlyRank-AI/`.
- [x] **Real work embedded**: All cases, charts, and bio are real assets—zero placeholder text.
- [x] **Real person reaction captured**: Detailed feedback from a Senior ML Engineer documented.
- [x] **No mystery code**: Full technical understanding of HTML5, CSS tokens, and JS logic verified.
- [x] **Honest "still ugly" list present**: 3 specific rough edges documented.
