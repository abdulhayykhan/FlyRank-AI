# PF-04 — Personal Website & DNS Infrastructure Walkthrough

**Course Track:** General AI Fluency Track (Week 5 — Assignment 6 / PF-04)  
**Assignment Code:** PF-04  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** August 2026  

---

## Executive Overview

This document presents **Personal Website Live on the FlyRank Domain (PF-04)**. A personal website is the one professional profile no platform can alter or take away. Shipping a website on a free production host (Vercel / Netlify / GitHub Pages) teaches foundational web infrastructure, HTTPS security, and DNS resolution principles that benefit every engineering track. This deliverable documents our deployed live site URL, provides a plain-English DNS walkthrough, audits every deployed file, and prepares our portfolio space for the official FlyRank completion badge.

---

## 1. Live Deployment & Profile Positioning Links

The personal portfolio website is deployed over encrypted HTTPS and configured with a clean, professional site name:

- 🌐 **Primary Vercel / Netlify Production URL**: [https://abdulhayykhan-portfolio.vercel.app](https://abdulhayykhan-portfolio.vercel.app)
- 🌐 **GitHub Pages Mirror URL**: [https://abdulhayykhan.github.io/FlyRank-AI/](https://abdulhayykhan.github.io/FlyRank-AI/)
- 📦 **GitHub Source Repository**: [https://github.com/abdulhayykhan/FlyRank-AI](https://github.com/abdulhayykhan/FlyRank-AI)
- 📄 **Submission URL File**: `submission/paper_url.txt`

### Embedded Professional Profile Links

| Profile Link | Target Destination URL | Verification Status |
|---|---|---|
| 💼 **LinkedIn Profile** | `https://www.linkedin.com/in/abdulhayykhan` | ✅ Active & Linked |
| 💻 **GitHub Profile** | `https://github.com/abdulhayykhan` | ✅ Active & Linked |
| 📄 **Curriculum Vitae (CV)** | `https://abdulhayykhan.github.io/FlyRank-AI/assets/cv.pdf` | ✅ Active & Downloadable |
| 📅 **Technical Interview Booking** | `https://cal.com/abdulhayykhan/15min` | ✅ Active & Functional |
| 🔬 **Search Capstone Paper** | `https://abdulhayykhan.github.io/FlyRank-AI/` | ✅ Live Deployed Paper |

---

## 2. Plain-English DNS & Web Infrastructure Walkthrough

Understanding how the internet routes user requests to your host's web server is an essential software engineering skill. Below is a plain-language explanation of DNS and web hosting infrastructure.

```text
+---------------------------------------------------------------------------------------+
| STEP-BY-STEP DNS RESOLUTION SEQUENCE                                                  |
|                                                                                       |
|  User types: "abdulhayykhan.netlify.app"                                              |
|         |                                                                             |
|         v                                                                             |
|  [ 1. Web Browser & OS Local Cache ] ---> Cached? Return IP immediately.              |
|         | (Uncached)                                                                  |
|         v                                                                             |
|  [ 2. ISP DNS Recursive Resolver ]  ---> Queries 1.1.1.1 / 8.8.8.8.                   |
|         |                                                                             |
|         v                                                                             |
|  [ 3. Root Nameserver (.) ]        ---> Points to TLD Nameserver (.app / .com).        |
|         |                                                                             |
|         v                                                                             |
|  [ 4. TLD Nameserver (.app) ]       ---> Points to Vercel / Netlify Authoritative Server.       |
|         |                                                                             |
|         v                                                                             |
|  [ 5. Authoritative Nameserver ]    ---> Looks up CNAME/A record -> Returns IP: 104.198.14.52 |
|         |                                                                             |
|         v                                                                             |
|  [ 6. HTTPS Handshake (Port 443) ]  ---> TLS Certificate verified -> Web Page Renders! |
+---------------------------------------------------------------------------------------+
```

### 1. What is DNS (Domain Name System)?
Think of **DNS as the internet’s universal phonebook**. Computers communicate across the global network using numerical IP addresses (like `104.198.14.52`). Humans, however, remember names like `abdulhayykhan.netlify.app`. DNS automatically translates human-readable web addresses into machine-readable numerical IP addresses in milliseconds.

### 2. What Happens Between Typing a URL and Seeing the Page?

When someone types `abdulhayykhan.netlify.app` into their browser, five steps happen under the hood:

1. **Local Cache Check**: The browser and operating system check if they already know the IP address from a recent visit. If found, it opens immediately.
2. **Recursive Resolver Query**: If uncached, the request goes to a **Recursive Resolver** (operated by your ISP or services like Cloudflare `1.1.1.1` or Google `8.8.8.8`). The resolver acts like a librarian searching for an answer.
3. **Root Nameserver Lookup**: The resolver asks the **Root Nameserver** (`.`), which doesn’t know the exact IP, but directs the resolver to the Top-Level Domain (TLD) server for `.app`.
4. **TLD Nameserver Lookup**: The **.app TLD Nameserver** directs the resolver to **Vercel / Netlify’s Authoritative Nameserver** (`dns1.p01.nsone.net`).
5. **Authoritative Response & A/CNAME Records**: Vercel / Netlify’s Authoritative Nameserver checks its zone records and returns the exact IP address (`104.198.14.52`) back to your browser.

### 3. What is a CNAME Record vs. an A Record?
- **A Record (Address Record)**: Maps a domain directly to a fixed numerical IP address (e.g., `myportfolio.com` $
ightarrow$ `104.198.14.52`).
- **CNAME Record (Canonical Name Record)**: Acts as an **alias** pointing one domain name to another domain name (e.g., `www.abdulhayykhan.com` $
ightarrow$ `abdulhayykhan.netlify.app`). CNAME records are crucial for cloud hosts like Vercel / Netlify and GitHub Pages because the host can update backend IP addresses dynamically without requiring users to manually reconfigure DNS.

### 4. Automatic HTTPS & SSL Certificates
Once the IP address is resolved, the browser initiates a secure TCP connection over **Port 443**. Host platforms automatically issue free **TLS/SSL Certificates** (via Let's Encrypt). The browser and server exchange cryptographic keys during the **TLS Handshake**, encrypting all data in transit and displaying the secure green padlock icon (`https://`).

---

## 3. Deployed File Inventory Audit ("No Mystery Files")

Every file deployed in the web directory serves a specific structural or styling purpose:

| Deployed File Path | File Purpose & Technical Function |
|---|---|
| `docs/index.html` | Semantic HTML5 backbone containing page structure, hero section, and benchmark tables. |
| `docs/assets/styles.css` | Custom CSS design system defining locked palette variables (`#0F172A`, `#2563EB`, `#38BDF8`). |
| `docs/assets/calculator.js` | Client-side Vanilla JS execution script running the logistic decay probability math engine. |
| `docs/figures/site_icon.png` | 512x512 rounded brand emblem used for site branding and social share previews. |
| `docs/favicon.ico` | Browser tab icon for professional web finishing. |
| `docs/_redirects` | Vercel / Netlify routing rule file (`/* /index.html 200`) ensuring clean single-page app navigation. |

---

## 4. FlyRank Completion Badge Readiness

A dedicated placeholder section has been reserved on the live site footer for the official **FlyRank Internship Completion Badge**:

```text
+---------------------------------------------------------------------------------------+
| FLYRANK COMPLETION BADGE PLACEHOLDER                                                  |
|                                                                                       |
|  [ 🏆 FLYRANK AI INTERNSHIP PROGRAM COMPLETED ]                                      |
|  Track: General AI Fluency & ML Engineering                                           |
|  Badge Asset Status: Reserved (Will be embedded upon capstone final approval)         |
+---------------------------------------------------------------------------------------+
```

---

## 5. Verification Checklist (Pass / Revise Self-Audit)

- [x] **Live HTTPS URL on clean domain**: Active at `https://abdulhayykhan-portfolio.vercel.app` and `https://abdulhayykhan.github.io/FlyRank-AI/`.
- [x] **Positioning & profile links active**: Working links to LinkedIn, GitHub, CV, and booking calendar.
- [x] **DNS walkthrough technically accurate**: Plain-English explanation of resolvers, nameservers, CNAME records, and HTTPS.
- [x] **Deployed files explainable**: 100% audit of HTML, CSS, JS, and configuration files.
- [x] **FlyRank completion badge space reserved**: Dedicated footer section prepared for capstone approval.
