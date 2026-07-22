# 🎥 Complete 5-Minute Capstone Showcase Video Recording Script

**Project Title:** Search Intelligence & Content Opportunity Scoring  
**Presenter:** Abdul Hayy Khan  
**Live Paper URL:** https://abdulhayykhan.github.io/FlyRank-AI/  
**GitHub Repository:** https://github.com/abdulhayykhan/FlyRank-AI  

---

## 🎬 Recording Preparation Checklist
1. **Screen Recorder**: Use OBS Studio, Loom, or Windows Game Bar (Win + Alt + R). Set resolution to 1080p (1920x1080).
2. **Browser Tabs Open in Order**:
   - **Tab 1**: Live Paper Web Page (`https://abdulhayykhan.github.io/FlyRank-AI/`)
   - **Tab 2**: GitHub Repository (`https://github.com/abdulhayykhan/FlyRank-AI`)
   - **Tab 3**: Jupyter Notebook / Colab (`work/notebooks/capstone.ipynb`)
   - **Tab 4**: Hugging Face Warehouse Dataset (`https://huggingface.co/datasets/FlyRank/internship-warehouse`)
3. **Audio**: Speak at a steady, confident pace.

---

## ⏱️ Second-by-Second Video Script (5 Minutes / 300 Seconds)

### PART 1: Introduction & Problem Statement (0:00 - 1:00)

| Timestamp | Visual (What to Show on Screen) | Spoken Script (What to Say) |
|---|---|---|
| **0:00 - 0:15** | Open **Tab 1 (Live Paper)**. Show the dark header with title *"Search Intelligence & Content Opportunity Scoring"*. Move your mouse over the author metadata and GitHub badges. | *"Hi everyone, I'm Abdul Hayy Khan, and welcome to my FlyRank AI Capstone Showcase: Search Intelligence and Content Opportunity Scoring. Today, I'm excited to present an end-to-end machine learning system built on production search data."* |
| **0:15 - 0:35** | Scroll down slightly to **Section 1: Introduction & Problem Statement**. Highlight the text discussing enterprise content decay. | *"In enterprise SEO, digital publications manage thousands of URLs. Over time, search intent evolves and algorithm layouts shift—causing high-performing pages to gradually decay in organic traffic. But here is the tension: traditional quarterly audits rely on naive age thresholds, like updating any page older than 180 days."* |
| **0:35 - 1:00** | Highlight the paragraph on static rule failure. | *"In our analysis, we discovered that 48% of stale content items are actually still growing in traffic! Static rules fail because age alone doesn't mean a page is dying—wasting thousands of dollars in unnecessary editorial rewrites. That's why we built a machine learning priority scoring framework."* |

---

### PART 2: Data Contract & Honest Validation Split (1:00 - 2:00)

| Timestamp | Visual (What to Show on Screen) | Spoken Script (What to Say) |
|---|---|---|
| **1:00 - 1:20** | Scroll to **Section 2: Data Contract**. Hover over the 5 plain-words contract answers and Hugging Face callout box. Quickly switch to **Tab 4 (Hugging Face)** and back. | *"Our model was evaluated on a 79-million-row production search dataset from Hugging Face, specifically a 30,000 enterprise content item slice. We established a strict data contract: 1 row equals 1 content item over a trailing 90-day feature window, predicting binary traffic decline."* |
| **1:20 - 1:40** | Scroll to **Section 3: Methodology & Validation Design**. Highlight the text **`GroupShuffleSplit` on `client_id`**. | *"Now, the most critical part of our methodology is how we split the data. Standard random train-test splits are naive because pages from the same client share domain authority. A random split lets the model memorize client domains rather than learning real signals, artificially inflating metrics by over 8%."* |
| **1:40 - 2:00** | Switch to **Tab 3 (Notebook)** and show the `GroupShuffleSplit` Python code cell. | *"To ensure complete honesty, we used a Client-Holdout Group Split using `GroupShuffleSplit` on `client_id`. This holds out whole client domains during evaluation, testing true out-of-sample generalization to brand new, unseen websites."* |

---

### PART 3: Results & The Key Chart (2:00 - 3:15)

| Timestamp | Visual (What to Show on Screen) | Spoken Script (What to Say) |
|---|---|---|
| **2:00 - 2:30** | Switch back to **Tab 1 (Live Paper)** and scroll to **Section 4: Results & Benchmark Evaluation**. Highlight the **Benchmark Comparison Table**. | *"Here are our benchmark results evaluated on held-out client domains. We compared four strategies on the exact same test split. Our Week 4 heuristic baseline rule achieved a Precision@50 of 0.340. Logistic Regression reached 0.400, and a depth-3 Decision Tree reached 0.540."* |
| **2:30 - 2:55** | Highlight the highlighted **Random Forest row** in the table (Precision@50 = 0.740). | *"Our final Random Forest model achieved a Precision@50 of 0.740 and a ROC-AUC of 0.750. Out of the top 50 pages flagged by the model, 37 are true declining pages—delivering a 2.18x directional lift over our baseline."* |
| **2:55 - 3:15** | Hover over **Figure 1 (Feature Importances)** and **Figure 2 (Precision@K Curve)**. | *"Looking at our feature importances in Figure 1, the model leans heavily on content staleness (28.4%), average position (22.1%), and 90-day log impressions (19.5%). Figure 2 shows our Precision@K curve consistently outperforming the random base rate across all top K cutoffs."* |

---

### PART 4: Content Action Playbook & Strict No-Go Rules (3:15 - 4:15)

| Timestamp | Visual (What to Show on Screen) | Spoken Script (What to Say) |
|---|---|---|
| **3:15 - 3:45** | Scroll to **Section 6: Content Action Playbook**. Highlight the **Archetype Table**. | *"A model score alone is useless without clear human actions. We mapped model scores into a Content Action Playbook. For example, Archetype A—pages with high exposure and staleness—triggers a Full Content Refresh. Archetype B—pages in striking distance with weak CTR—triggers a Title and Meta Description rewrite."* |
| **3:45 - 4:15** | Highlight the red **🛑 Strict Automation No-Go Rules** callout box. | *"Crucially, we established strict human-in-the-loop boundaries. Our No-Go list mandates: NO unassisted automated LLM writing or publishing, NO automated 301 redirects or page deletions, and NO automated alterations on legal or medical YMYL compliance content. AI supports human decisions; it doesn't replace them."* |

---

### PART 5: Reproducibility & Conclusion (4:15 - 5:00)

| Timestamp | Visual (What to Show on Screen) | Spoken Script (What to Say) |
|---|---|---|
| **4:15 - 4:40** | Scroll to **Section 7: Reproducibility** and **Section 8: Acknowledgments**. Click the link to **Tab 2 (GitHub Repository)**. | *"This entire project is 100% open-source and reproducible. All weekly notebooks, data contracts, metric JSON receipts, and exported figures are available in our GitHub repository. And a special thanks to FlyRank for providing access to production search datasets."* |
| **4:40 - 5:00** | Show the **GitHub Repo main page** and scroll to the live paper link in `README.md`. Smile/conclude! | *"You can read our live research paper at `abdulhayykhan.github.io/FlyRank-AI`. Thank you for watching, and I look forward to your questions!"* |

---
