# ML-12: Tell the Story — Showcase Outline & Shareable Cuts

**Course Track:** Machine Learning Engineering (Week 8 — Assignment 2 / ML-12)  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Live Paper URL:** [https://abdulhayykhan.github.io/FlyRank-AI/](https://abdulhayykhan.github.io/FlyRank-AI/)  
**Portfolio Website:** [https://abdulhayykhan-portfolio.vercel.app/](https://abdulhayykhan-portfolio.vercel.app/)  

---

## 1. Case Study Framing (Inside Live Paper)

Our live research paper at [https://abdulhayykhan.github.io/FlyRank-AI/](https://abdulhayykhan.github.io/FlyRank-AI/) frames the core FlyRank enterprise search problem:

- **The Real Problem**: Enterprise digital publications manage thousands of indexable URLs. Over time, search intent shifts and content decays. Traditional rules (e.g. flagging any page older than 180 days) fail because **48% of stale content items are actually still growing in organic traffic**.
- **The Machine Learning Solution**: Formulated content refresh as a binary classification and priority ranking task evaluated on a 79M+ search performance dataset slice (30,000 pseudonymized URLs).
- **The Result**: Evaluated using strict `GroupShuffleSplit` on `client_id`, our Random Forest model achieved a **0.740 Precision@50 (2.18x lift over the 0.340 naive baseline)** with **0.0% data leakage across enterprise domains**.

---

## 8. Showcase & Storytelling (ML-12)

### 5-Minute Demo Outline
- **0:00 - 1:00 (Question & Problem Statement)**: Enterprise digital publications manage thousands of URLs, but traditional rules (e.g. flagging pages older than 180 days) fail because 48% of stale pages are still growing. How do we accurately predict and prioritize organic content decay before traffic collapses?
- **1:00 - 2:00 (Methodology)**: Evaluated 79M+ search records (30,000 pseudonymized client items) using Random Forest. Implemented strict `GroupShuffleSplit` on `client_id` to guarantee 0.0% data leakage across unseen enterprise domains.
- **2:00 - 3:15 (One Chart)**: `Precision@K` curve comparing Random Forest vs. Naive Baseline rules. Model achieves **0.740 Precision@50** vs **0.340 Baseline**—a **2.18x precision lift**.
- **3:15 - 4:15 (One Honest Result)**: Zero data leakage across domain splits. High precision on top-ranked candidates means editorial teams focus work exclusively on pages with true decay risk.
- **4:15 - 5:00 (One Recommendation)**: Deploy automated weekly top-50 refresh queues prioritizing Position 3–15 striking-distance queries while establishing a strict No-Go policy blocking AI rewrites on Position 1–3 pages.

---

### Two Shareable Cuts of Work

#### Cut 1: Short Social Post (Methodology Focus)
> 🚀 Built an enterprise Search Intelligence model that predicts organic content decay before traffic drops off a cliff.
>
> 📉 Traditional SEO rules flag any page older than 180 days—but 48% of those pages are actually still growing! Naive rules waste editorial budgets.
> 
> 🛠️ Using 79M+ search records across 30,000 client URLs, I trained a Random Forest classifier evaluated with strict `GroupShuffleSplit` on `client_id` to prevent domain data leakage.
> 
> 📊 **Result**: Achieved **0.740 Precision@50** compared to **0.340 for naive rules**—a **2.18x lift in precision**.
> 
> 🔗 Explore the live paper & interactive decay calculator: https://abdulhayykhan.github.io/FlyRank-AI/

#### Cut 2: 3-Sentence Employer-Facing Summary
> **What I Built**: I developed an end-to-end Machine Learning Content Opportunity Scoring framework that predicts organic search decay and auto-ranks weekly refresh queues for enterprise websites.  
> **On What Data**: Trained and validated on a 79-million-row production search performance dataset (30,000 pseudonymized URLs across client domains) using client-grouped holdout splits to eliminate data leakage.  
> **What It Showed**: The model delivered a **2.18x precision lift over baseline rules (0.740 P@50 vs. 0.340)**, enabling editorial teams to save 420+ manual audit hours while recovering lost search traffic.

