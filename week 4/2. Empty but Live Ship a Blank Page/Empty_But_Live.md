# Empty but Live: Ship a Blank Page

**Course Track:** General AI Fluency Track (Week 4 — Assignment 2)  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** July 2026  

---

## Executive Overview

This document presents **Empty but Live: Ship a Blank Page (Week 4 Assignment 2)**. Going from nothing to a live, publicly reachable URL is the single most critical milestone in portfolio construction. Shipping an initial live skeleton shell removes deployment friction early—transforming the build phase from starting at zero to populating a working live web page. This deliverable documents live host configuration on GitHub Pages, multi-device reachability verification, and the unified Claude Project workspace setup containing our identity kit, case studies, and content map.

---

## 1. Live Deployment & Host Configuration

The portfolio project shell was connected to a free, production-grade static host via GitHub Pages:

- 🌐 **Public Live URL**: [https://abdulhayykhan.github.io/FlyRank-AI/](https://abdulhayykhan.github.io/FlyRank-AI/)
- 📦 **GitHub Repository**: [https://github.com/abdulhayykhan/FlyRank-AI](https://github.com/abdulhayykhan/FlyRank-AI)
- 📂 **Deployment Branch & Source**: Branch `main` $ightarrow$ Directory `/docs`
- 📄 **Mandatory Submission Record**: `submission/paper_url.txt` (contains single line: `https://abdulhayykhan.github.io/FlyRank-AI/`)

```text
+---------------------------------------------------------------------------------------+
| GITHUB PAGES DEPLOYMENT PIPELINE                                                       |
+---------------------------------------------------------------------------------------+
  Local Workspace (FlyRank-AI/docs/index.html)
        |
        v
  Git Commit & Push (origin/main)
        |
        v
  GitHub Pages Builder (Serving /docs Directory)
        |
        v
  Live Production URL: https://abdulhayykhan.github.io/FlyRank-AI/
+---------------------------------------------------------------------------------------+
```

---

## 2. Multi-Device Reachability Verification

To confirm the live URL is accessible globally and free of local localhost caching bias, reachability was verified across multiple devices and viewports:

| Device & Browser Test | Verification Status | Observed Result |
|---|---|---|
| **Laptop / Desktop (Chrome)** | ✅ **VERIFIED** | Renders 3D header, glass navbar, progress bar, and tabbed benchmarks. |
| **Mobile Phone (Safari / Chrome)** | ✅ **VERIFIED** | Renders responsive single-column layout, touch-friendly tab buttons, and scaled charts. |
| **External Network Check** | ✅ **VERIFIED** | Reachable over public HTTPS without local network or session authentication. |

---

## 3. Claude Project Unified Build Workspace

To ensure the build week proceeds with total context alignment, all foundational decisions (Identity Kit, Case Study, and Content Map) were compiled into a single custom instruction prompt inside the **`FlyRank AI Capstone Build`** Claude Project:

```text
=== CLAUDE PROJECT UNIFIED BUILD INSTRUCTIONS ===

Project Name: FlyRank AI Capstone Build
Author: Abdul Hayy Khan (3rd Year AI Student at DUET & ML Intern at FlyRank AI)
Live Deployed URL: https://abdulhayykhan.github.io/FlyRank-AI/

1. Identity Kit Tokens:
   - Typography: Newsreader (Headings), Plus Jakarta Sans (Body), JetBrains Mono (Code).
   - Hex Colors: #0F172A (Text), #F8FAFC (Background), #2563EB (Brand Blue), #38BDF8 (Accent).
   - Mood: Calm, high-contrast academic-meets-engineering aesthetic.

2. Lead Case Study (Lane 2 Search Intelligence):
   - Problem: Enterprise content decay; 48% of stale content is still growing.
   - Decisions: 90-day feature window, GroupShuffleSplit on client_id (0% leakage).
   - Outcome: Random Forest 0.740 Precision@50 vs 0.340 Baseline Rule (2.18x lift).

3. Content Map & Conversion Goal:
   - One-Line Claim: "I build leak-free machine learning decision-support systems that predict enterprise organic search decay, achieving a 0.740 Precision@50 (2.18x baseline lift) on production data."
   - Ultimate Conversion Goal: Schedule a 15-Minute Technical Interview.
```

---

## 4. Verification Checklist (Pass / Revise Self-Audit)

- [x] **Reachable public URL exists**: `https://abdulhayykhan.github.io/FlyRank-AI/` live on GitHub Pages.
- [x] **Multi-device verified**: Confirmed on both desktop laptop and mobile phone browsers.
- [x] **Matches stack from previous assignment**: Deployed directly from `/docs` HTML/CSS/JS stack on GitHub Pages.
- [x] **Claude Project loaded**: Identity Kit, Case Study 3 Beats, and Content Map integrated into project instructions.
