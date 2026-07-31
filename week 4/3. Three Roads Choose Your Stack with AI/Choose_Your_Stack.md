# Three Roads: Choose Your Stack with AI

**Course Track:** General AI Fluency Track (Week 4 — Assignment 3)  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** July 2026  

---

## Executive Overview

This document presents **Three Roads: Choose Your Stack with AI (Week 4 Assignment 3)**. Selecting a technology stack is a core AI-fluency decision. Rather than blindly accepting an AI recommendation, this assignment inputs our exact operational constraints into AI, evaluates three stack options ranging from simplest to most powerful, pressure-tests the front-runner, and documents a written rationale explaining our choice.

---

## 1. Input Operational Constraints

The AI was provided with four explicit constraints matching our project reality:

1. 💰 **Constraint 1 (Free Tier Only)**: Total deployment and hosting cost must be exactly **$0.00**.
2. 🛠️ **Constraint 2 (Honest Skill Level)**: 3rd Year Artificial Intelligence Student with high Python/Data Science proficiency and solid core HTML5/CSS3/Vanilla JS skills. Prefers fast, reliable execution over wrestling with complex JS framework build scripts.
3. 📐 **Constraint 3 (Portfolio Content Map)**: Must present our 79M-row Search Intelligence Capstone, benchmark comparison tables, feature importance charts, author bio, and an interactive Content Priority Calculator.
4. ⚙️ **Constraint 4 (Display Needs & Dynamic Backend Status)**: Needs clean GFM table formatting, high-res chart embeds, and an in-page interactive JS calculator.  
   - **Backend Status**: **Not yet required**. Client-side JavaScript math is 100% sufficient to run probability scoring locally in the browser without deploying or paying for a server backend.

---

## 2. The Three Stack Options Evaluated

```text
========================================================================================
                          THREE STACK ROADS EVALUATED
========================================================================================

  [ ROAD 1: SIMPLEST ]               [ ROAD 2: BALANCED (FRONT-RUNNER) ]      [ ROAD 3: MOST POWERFUL ]
  No-Code / Framer / Notion          Vanilla HTML5 / CSS3 / JS               Next.js + Tailwind + Vercel
  - Host: Framer Free                - Host: GitHub Pages (Free)              - Host: Vercel Free
  - Backend: None                    - Backend: None (Pure Static + JS)       - Backend: Optional Serverless
  - Trade-off: Custom JS & CSS      - Trade-off: Manual HTML editing,      - Trade-off: Heavy npm dependencies,
    tokens locked behind paywall       but 100% control & 0 build friction    SSR hydrations, build overhead
========================================================================================
```

### Comparative Stack Comparison Table

| Stack Dimension | Road 1: Simplest (Framer / No-Code) | 🏆 Road 2: Balanced (Vanilla HTML5/CSS3/JS) | Road 3: Most Powerful (Next.js + Vercel) |
|---|---|---|---|
| **Build Method** | Drag-and-drop visual builder. | Hand-crafted semantic HTML5 & modular CSS. | React App Router, TypeScript, Tailwind. |
| **Hosting Platform** | Framer Free Domain. | **GitHub Pages** (Serving `/docs` directory). | Vercel Free Tier. |
| **Backend Need** | None. | **None (Pure client-side JS math)**. | Optional Vercel Serverless Functions. |
| **Identity Kit Match** | Limited (Custom fonts require paid plans). | **100% Exact** (Custom Google Fonts & CSS variables). | High (Requires Tailwind config setup). |
| **Core Trade-off** | Fast to launch, but custom JS widgets and tables break. | Requires manual HTML tags, but **zero build errors**. | Extremely powerful, but high maintenance & build churn. |

---

## 3. Pressure-Testing the Front-Runner (Road 2)

Before locking in our choice, Road 2 (Vanilla HTML5 / CSS3 / Vanilla JS + GitHub Pages) was pressure-tested against four critical evaluation questions:

1. ❓ *What breaks if I pick the simplest option (Road 1)?*  
   **Answer**: In Road 1, embedding our interactive Content Priority Calculator widget requires paid Framer tiers or custom iframe injections. Custom CSS variables (`#0F172A`, `#2563EB`) and monospace code formatting get compromised.
2. ❓ *What do I maintain if I pick the most powerful option (Road 3)?*  
   **Answer**: In Road 3, I would have to maintain a complex `node_modules` dependency tree, React state hooks, and Next.js build pipelines. A minor package version mismatch could break deployment right before the deadline.
3. ❓ *Can I finish in two weeks?*  
   **Answer**: **Yes, effortlessly.** Road 2 has zero build steps. Editing `index.html` or `index.css` reflects instantly in the browser and deploys to GitHub Pages in under 30 seconds.
4. ❓ *Does it show my work the way it needs to be shown?*  
   **Answer**: **Exceptionally well.** It provides complete control over GFM benchmark tables, high-resolution Matplotlib chart figures, and interactive DOM manipulation for the calculator widget.

---

## 4. Written Stack Rationale (In My Own Words)

> *"I have chosen **Road 2: Vanilla HTML5, Custom CSS3, and Vanilla JavaScript hosted on GitHub Pages**.
> 
> I rejected **Road 1 (Framer/No-Code)** because drag-and-drop builders lock custom JavaScript widgets and exact CSS typography tokens behind paywalls, preventing me from showing my interactive priority calculator.
> 
> I rejected **Road 3 (Next.js/Tailwind/Vercel)** because React framework compilation, Node build dependencies, and SSR hydrations create unnecessary technical debt for a static research paper. As a 3rd Year AI Student focusing on machine learning algorithms, my time is best spent refining model validation and technical storytelling—not debugging npm package conflicts.
> 
> **Can I maintain this?** Yes. Vanilla HTML5 and CSS3 are evergreen standards. There are no npm packages to update or breaking framework migrations to handle.
> 
> **Does it need a backend?** Not yet. The priority calculator runs entirely on client-side JS math in the user's browser, eliminating server hosting costs and backend API latency."*

---

## 5. Verification Checklist (Pass / Revise Self-Audit)

- [x] **Three genuine options evaluated**: Framer (Simplest), Vanilla HTML5/JS (Balanced), Next.js (Most Powerful).
- [x] **Chosen stack is free & matched to needs**: $0 GitHub Pages hosting displaying ML research and interactive widget.
- [x] **Rationale in own words**: Rationale explicitly covers maintainability, trade-offs, and skill alignment.
- [x] **Backend question answered honestly**: Confirmed "not yet" (pure client-side static + JS math).
