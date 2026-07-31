# Decide Once: Build Your Identity Kit

**Course Track:** General AI Fluency Track (Week 3 — Assignment 2)  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** July 2026  

---

## Executive Overview

This document presents **Decide Once: Build Your Identity Kit (Week 3 Assignment 2)**. A consistent, intentional visual identity separates a portfolio that feels unified from one that feels thrown together. By locking key typography, color palette tokens, logo/favicon assets, and standing style instructions once, every research paper, case study, and interactive UI component automatically inherits a calm, high-contrast aesthetic where quantitative engineering results remain the loudest element on the page.

---

## 1. Typography Selection (Google Fonts)

To balance academic research paper credibility with modern web application UI legibility, two complementary free Google Fonts were selected:

| Type Category | Font Family | Style / Weight | Purpose & Rationale |
|---|---|---|---|
| **Heading Font** | **Newsreader** | Serif (SemiBold 600) | Establishes academic rigor, editorial authority, and paper headline structure. |
| **Body Font** | **Plus Jakarta Sans** | Sans-Serif (Medium 500, Regular 400) | Maximizes UI legibility, smooth mobile reading, and clean technical narrative. |
| **Monospace / Code** | **JetBrains Mono** | Monospace (Medium 500) | Precise rendering of SQL/Python code blocks, schemas, and metric tables. |

---

## 2. Tight Color Palette (Hex Codes)

The color palette is deliberately kept calm and restrained (4 core tokens) so that quantitative data visualizations, Precision@K curves, and model benchmarks dominate reader attention.

### Color Tokens & Hex Codes Table

| Token Name | Light Mode Hex | Dark Mode Hex | Usage & Purpose |
|---|---|---|---|
| **Near-Black Text** | `#0F172A` | `#F9FAFB` | Primary body text and high-contrast headlines. |
| **Near-White BG** | `#F8FAFC` | `#090D16` | Clean page canvas background with zero visual clutter. |
| **Brand Primary** | `#2563EB` | `#60A5FA` | Active links, primary CTA buttons, and highlighted metric cards. |
| **Soft Accent** | `#38BDF8` | `#38BDF8` | Interactive hover states, glow borders, and chart trend lines. |

---

## 3. Logo & Favicon Identity Asset

A clean, minimalist logo badge and site favicon were generated and implemented across the live research paper site [`https://abdulhayykhan.github.io/FlyRank-AI/`](https://abdulhayykhan.github.io/FlyRank-AI/):

- **Monogram Icon Asset**: `docs/figures/site_icon.png` (512x512 PNG) & `docs/favicon.ico`.
- **Design Concept**: Rounded royal blue shield (`#2563EB`) featuring stylized white signal bars and a sky blue (`#38BDF8`) trend arrow vector—symbolizing search intelligence performance gains.

```text
+-------------------------------------------------------------+
|                      SITE FAVICON LOGO                      |
|                                                             |
|                    [  ( 🧠 FlyRank AI )  ]                  |
|               3D Gradient Emblem & Trend Vector             |
|                  Hex: #2563EB | Accent: #38BDF8             |
+-------------------------------------------------------------+
```

---

## 4. Two-Line Standing Style Note

The following style note was added to my **Claude Project Custom Instructions** as a standing rule so all generated web pages and markdown artifacts maintain strict visual alignment:

```text
=== CLAUDE PROJECT STANDING STYLE NOTE ===

Line 1 (Typography & Hex Tokens):
Fonts: Newsreader (Headings), Plus Jakarta Sans (Body), JetBrains Mono (Code). Colors: #0F172A (Text), #F8FAFC (BG), #2563EB (Brand Blue), #38BDF8 (Accent).

Line 2 (Visual Mood & Constraint):
A calm, high-contrast academic-meets-engineering visual identity where quantitative results, benchmark tables, and live research remain the loudest elements on the page.
```

---

## 5. Verification & Implementation Status

- [x] **Typography Locked**: Newsreader (Headings) + Plus Jakarta Sans (Body) + JetBrains Mono (Code).
- [x] **Palette Locked**: 4 tight colors with exact hex codes (`#0F172A`, `#F8FAFC`, `#2563EB`, `#38BDF8`).
- [x] **Logo & Favicon Deployed**: Configured `site_icon.png` and `favicon.ico` on GitHub Pages.
- [x] **Claude Project Updated**: Two-line standing style note added to custom project instructions.
