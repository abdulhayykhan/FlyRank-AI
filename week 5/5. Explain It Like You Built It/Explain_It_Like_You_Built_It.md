# Explain It Like You Built It

**Course Track:** General AI Fluency Track (Week 5 — Assignment 5)  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** August 2026  

---

## Executive Overview

This document presents **Explain It Like You Built It [Week 5 Assignment 5]**. The line between *"I built this"* and *"AI built something I can't explain"* is the core credibility boundary employers test. You don't have to write every line from scratch, but you must genuinely own and understand what you ship. This deliverable picks one real piece of our production build—the **Client-Side Content Priority Calculator Engine** embedded on our live web paper ([`https://abdulhayykhan.github.io/FlyRank-AI/`](https://abdulhayykhan.github.io/FlyRank-AI/))—and explains how it works in plain, simple words as if teaching a non-technical friend.

---

## 1. The Real Piece of Build Chosen

- **Selected Component**: *Client-Side Content Priority Calculator Engine* (`docs/index.html` & `docs/assets/calculator.js`).
- **Function**: Takes user input sliders for `days_since_last_update` and `avg_position`, calculates organic search content decay probability in real time, and dynamically updates the UI progress bar.

---

## 2. Explain It Like I'm Teaching a Friend

Imagine you’re explaining this interactive tool to a friend who has never written a line of code or built a website before:

```text
+---------------------------------------------------------------------------------------+
| HOW THE CLIENT-SIDE PRIORITY CALCULATOR WORKS (PLAIN-ENGLISH STEPS)                  |
|                                                                                       |
|  [ STEP 1: LISTEN ]             [ STEP 2: CALCULATE ]          [ STEP 3: UPDATE ]    |
|  User moves slider             JavaScript runs sigmoid        DOM updates score text |
|  (e.g., 180 days stale)  --->  math formula in-browser  --->  and turns bar red       |
|                                (Runs in < 1 millisecond)      (Zero page reload)      |
+---------------------------------------------------------------------------------------+
```

### The Metaphor: The Doctor's Risk Assessment
Think of this calculator like a doctor checking two vital signs to score a patient's health risk—except here, the "patient" is a blog post on Google, and the "disease" is losing search traffic.

### Step 1: Listening to the Sliders (Event Listeners)
When a user drags the "Days Stale" slider on the web page, the web browser constantly triggers a tiny listening function in JavaScript called an `addEventListener('input')`. It instantly catches the exact number your finger moved to—say, `180 days`—without requiring you to press a "Submit" button.

### Step 2: The Math Engine (The Logistic Sigmoid Formula)
Once JavaScript gets those numbers (`days_stale = 180`, `search_position = 9.5`), it feeds them into a mathematical equation called a **logistic sigmoid function**:

$$z = -2.5 + (0.015 \cdot 	ext{days\_stale}) + (0.08 \cdot 	ext{avg\_position})$$

$$	ext{Decay Risk Score (\%)} = rac{100}{1 + e^{-z}}$$

What does this equation actually do? It takes any combination of big and small numbers and "squashes" them into a clean percentage score between 0% and 100%. If a page is old and slipping in rank, $z$ goes up, and the formula outputs an **88% Decay Risk**.

### Step 3: Changing the Screen Instantly (DOM Manipulation)
Here is where the magic happens: JavaScript directly reaches into the webpage's live blueprint (called the **DOM**, or Document Object Model). With one line of code:

`document.getElementById('risk-score').innerText = score + '%';`

JavaScript replaces the text on screen from `0%` to `88%` and changes the visual progress bar's color from green to vibrant red. 

---

## 3. Why This Architecture Matters (The Technical Lesson Learned)

### Why Client-Side JS Beats a Server Backend for Static Papers:
- ⚡ **Zero Latency (< 1ms)**: Because the math runs locally inside your web browser's RAM, the UI updates instantly without waiting for a server across the internet to respond.
- 💰 **$0 Hosting Cost**: It requires zero server infrastructure (no Node.js, Python Flask, or AWS servers to maintain). It runs 100% free on GitHub Pages.
- 🛡️ **Zero Maintenance Debt**: There are no database connections to break or API endpoints to update over time.

---

## 4. Verification Checklist (Pass / Revise Self-Audit)

- [x] **Real piece of build selected**: Client-side Priority Calculator from live website (`docs/index.html`).
- [x] **In own words & technically correct**: Clear plain-words explanation using the "doctor risk assessment" metaphor.
- [x] **Demonstrates genuine learning**: Explains event listeners, sigmoid math logic, and DOM updates cleanly.
