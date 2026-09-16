# FlyRank Machine Learning Engineering Internship — Capstone & Track Repository

**Intern:** Abdul Hayy Khan  
**Role / Track:** Machine Learning Engineering Intern (Machine Learning Track — Code: ML)  
**Institution:** 3rd Year Artificial Intelligence Student, Dawood University of Engineering & Technology (DUET)  
**Primary Research Lane:** Lane 2 — Refresh / Content Opportunity Scoring  
**Deployed Research Paper:** [https://abdulhayykhan.github.io/FlyRank-AI/](https://abdulhayykhan.github.io/FlyRank-AI/)  
**Personal Portfolio Website:** [https://abdulhayykhan-portfolio.vercel.app/](https://abdulhayykhan-portfolio.vercel.app/)  
**GitHub Repository:** [https://github.com/abdulhayykhan/FlyRank-AI](https://github.com/abdulhayykhan/FlyRank-AI)  

---

## 🔬 Executive Overview

This repository contains the complete 8-week Machine Learning Engineering Track codebase, executed Jupyter Capstone notebooks, production evaluation scripts, and deployed research paper artifacts for the **FlyRank ML Engineering Internship**.

The capstone project formulates enterprise organic search decay as a binary classification and priority ranking problem. Using a 79M+ search performance dataset slice (30,000 pseudonymized URLs across enterprise client domains), we built a Random Forest scoring engine evaluated with strict `GroupShuffleSplit` on `client_id` to eliminate domain data leakage. The resulting model achieves **0.740 Precision@50 (a 2.18x lift over the 0.340 naive baseline)** and generates automated weekly refresh recommendations with human-in-the-loop editorial boundaries.

---

## 📂 Repository Directory Tree (Machine Learning Track)

```text
FlyRank AI/
├── README.md                                   # Root ML track overview & curriculum guide
├── Portfolio/                                  # Next.js 15 portfolio website (Vercel deployment)
├── assets/                                     # Visual assets & Abdul_Hayy_Khan_Resume.pdf
├── data/                                       # Processed ML datasets & feature vectors
├── docs/                                       # Deployed GitHub Pages research paper web app
├── notebooks/                                  # Executed Jupyter Capstone notebooks (W01–W08)
├── outputs/                                    # Model metrics JSON, refresh queues & PDF reports
├── scripts/                                    # Modular Python ML data pipeline & model scripts
├── skills/                                     # Agent skills for ML engineering workflows
├── submission/                                 # Official submission record (paper_url.txt)
├── week 1/
│   ├── 1. Run the Starter Notebooks/           # Environment setup & baseline discovery
│   └── 2. Research Question and Provisional Lane/ # W01 Research Question (Lane 2 Lock)
├── week 2/
│   ├── 1. Frame Your Lane as an ML Task/       # W02 Task framing, target label & loss function
│   ├── 2. VIDEO Machine Learning/              # ML systems architecture notes
│   ├── 3. Frame It as Cases/                   # ML case study framing
│   └── 4. The Prompt Ladder/                   # Prompt engineering for ML pipelines
├── week 3/
│   └── 1. Search Intelligence Data Contract/   # W03 Data contract, features & GroupShuffleSplit
├── week 4/
│   └── 1. Baseline Action Score and Top-10 Review/ # W04 Naive baseline rule evaluation (P@50 = 0.340)
├── week 5/
│   └── 1. Capstone Modeling Lane/              # W05 Random Forest model training & hyperparameter tuning
├── week 6/
│   └── 1. Validation and Research Claim Audit/ # W06 Zero-leakage audit & claim verification
├── week 7/
│   └── 1. Content Action Playbook/             # W07 Content action engine & No-Go policies
├── week 8/
│   ├── 1. Ship the Paper/                      # W08 Capstone paper & notebook finalization
│   └── 2. Tell the Story/                      # ML-12 Showcase demo outline & shareable cuts
└── work/                                       # Model figures, outputs, notebooks & storytelling
```

---

## 📊 Machine Learning Curriculum & Milestone Matrix

| Week & Code | Module / Assignment Title | Technical Deliverable & Milestone Summary |
|---|---|---|
| **Week 1 (W01)** | **Starter Notebooks & Research Question** | Locked Lane 2 (Refresh Scoring); aggregated 79M+ search records across 30k client URLs. |
| **Week 2 (W02)** | **Frame Your Lane as an ML Task** | Defined binary decay target label (`is_decaying`), evaluation metrics (Precision@K, AUCPR), and loss function. |
| **Week 3 (W03)** | **Search Intelligence Data Contract** | Engineered zero-shot features and designed `GroupShuffleSplit` on `client_id` for zero-leakage validation. |
| **Week 4 (W04)** | **Baseline Action Score & Review** | Evaluated naive threshold rules (e.g. `days_stale > 180`), establishing baseline **0.340 Precision@50**. |
| **Week 5 (W05)** | **Capstone Modeling Lane** | Trained Random Forest classifier, achieving **0.740 Precision@50 (2.18x lift over baseline)**. |
| **Week 6 (W06)** | **Validation & Research Claim Audit** | Audited feature importance and verified zero domain leakage across unseen client test splits. |
| **Week 7 (W07)** | **Content Action Playbook** | Built automated top-50 weekly refresh queue with reason codes and strict No-Go editorial policies. |
| **Week 8 (W08)** | **Ship the Paper & Tell the Story (ML-12)** | Deployed public research paper web app at GitHub Pages and authored 5-minute showcase demo script. |
| **ML-CAP-01** | **Final Capstone Submission** | Completed 9-section research paper, verified `submission/paper_url.txt`, and finalized repo. |

---

## 🏆 Key Empirical Benchmark Results

```text
+---------------------------------------------------------------------------------------+
| MODEL VS. BASELINE PERFORMANCE (GroupShuffleSplit Holdout Test Set)                  |
|                                                                                       |
|  Metric                     Naive Baseline Rule     Random Forest Model   Precision Lift |
|  -----------------------------------------------------------------------------------  |
|  Precision@10               0.400                   0.800                 2.00x Lift      |
|  Precision@25               0.360                   0.760                 2.11x Lift      |
|  Precision@50 (Primary)     0.340                   0.740                 2.18x Lift      |
|  Data Leakage Rate          0.0%                    0.0%                  Zero-Leakage    |
+---------------------------------------------------------------------------------------+
```

---

## 🌐 Submission Links

- 🔬 **Deployed Research Paper**: [https://abdulhayykhan.github.io/FlyRank-AI/](https://abdulhayykhan.github.io/FlyRank-AI/)
- 💻 **Portfolio Website**: [https://abdulhayykhan-portfolio.vercel.app/](https://abdulhayykhan-portfolio.vercel.app/)
- 📦 **GitHub Repository**: [https://github.com/abdulhayykhan/FlyRank-AI](https://github.com/abdulhayykhan/FlyRank-AI)
- 📄 **Direct Resume PDF**: [https://abdulhayykhan.github.io/FlyRank-AI/assets/Abdul_Hayy_Khan_Resume.pdf](https://abdulhayykhan.github.io/FlyRank-AI/assets/Abdul_Hayy_Khan_Resume.pdf)

---

## 📄 Acknowledgments & Data Credit

Built on the **[FlyRank](https://flyrank.ai)** ML Internship dataset.
