# Zerodha Kite + Coin — UX Audit & Unified Investment Flow Redesign

> **A UX research and design case study examining why India's most trusted broker forces 13M+ users to juggle two separate apps — and a surgical redesign proposal that adds MF integration without touching Kite's world-class trading tools.**

---

## 📋 Table of Contents

- [Problem](#problem)
- [Research Process](#research-process)
- [Key Insights](#key-insights)
- [Solution](#solution)
- [Wireframes](#wireframes)
- [Before / After](#before--after)
- [PRD Summary](#prd-summary)
- [Expected Metrics](#expected-metrics)
- [Deliverables](#deliverables)
- [Tools Used](#tools-used)

---

## Problem

Zerodha users who invest in both equities and mutual funds must operate **two separate apps**:

| App | Purpose | Users |
|-----|---------|-------|
| **Kite** | Stocks, ETFs, F&O trading | 13M+ |
| **Coin** | Direct mutual fund investments | Subset of Kite users |

Despite sharing a **single demat account**, neither app knows the other exists. The result:

- 🔴 **No unified portfolio view** — users cannot see their total net wealth in one screen
- 🔴 **Mandatory app switch mid-invest-flow** — to invest in a stock AND set up a SIP requires leaving Kite entirely
- 🔴 **Duplicate search systems** — searching "HDFC" in Kite never shows HDFC Flexi Cap Fund
- 🔴 **Broken mental model** — users think of "my Zerodha account" as one thing; the system presents two disconnected worlds

**Every major competitor has solved this:**
- ✅ Angel One — unified app, single search, combined portfolio
- ✅ Groww — unified app, best MF discovery UX in India
- ✅ Upstox — unified app

---

## Research Process

### Phase 1 — Heuristic Evaluation

Evaluated Kite and Coin against **Nielsen's 10 Usability Heuristics**. Key findings:

| Heuristic | Kite | Coin | Severity |
|-----------|------|------|----------|
| H2 — Match system to real world | 2/5 | 2/5 | 🔴 Critical |
| H4 — Consistency and standards | 2/5 | 2/5 | 🔴 Critical |
| H6 — Recognition over recall | 3/5 | 3/5 | 🟡 Significant |
| H1 — Visibility of system status | 3/5 | 3/5 | 🟡 Significant |
| H5 — Error prevention | 5/5 | 4/5 | 🟢 Pass |

**Positive finding preserved:** Kite's "slide to buy" + OTP confirmation mechanic is excellent error prevention for high-stakes equity orders. This is intentional friction that must survive the redesign.

### Phase 2 — User Journey Mapping

**Task: "Invest ₹5,000 — ₹3,000 in HDFC Bank stock + ₹2,000 in Parag Parikh Flexi Cap SIP"**

```
ZERODHA (current state):
Open Kite → Search HDFCBANK → Tap stock → Swipe → Choose NSE/BSE →
Calculate qty (mental math) → Slide to buy → OTP →
⚡ SWITCH TO COIN ⚡ → Re-orient → Search fund → Select Direct →
Choose SIP → Set amount → Set date → Confirm → OTP → Invest
= 14 screens · 1 app switch · ~5–6 minutes · 0 combined portfolio views

ANGEL ONE (benchmark):
Open app → Search HDFCBANK → Buy → qty → confirm →
Tap MF tab (same app) → Find Parag Parikh → SIP → ₹2,000 → date → Invest
= 7 screens · 0 app switches · ~2–3 minutes · combined portfolio visible
```

### Phase 3 — Competitive Analysis

| Dimension | Zerodha | Angel One | Groww | Upstox |
|-----------|---------|-----------|-------|--------|
| Single app (stocks + MF) | ❌ Two apps | ✅ | ✅ | ✅ |
| Global search | ❌ Separate | ✅ | ✅ | ✅ |
| Unified portfolio | ❌ Two views | ✅ | ✅ | ~Partial |
| Stock charting depth | ⭐⭐⭐⭐⭐ Best | ⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐ |
| F&O tooling | ⭐⭐⭐⭐⭐ Best | ⭐⭐⭐ | ⭐ | ⭐⭐⭐ |
| MF direct plan (₹0) | ✅ Via Coin | ❌ Regular | ✅ | ~Partial |
| MF discovery UX | ~Adequate | ✅ Good | ⭐⭐⭐⭐⭐ Best | ~Adequate |
| UI consistency | ❌ Kite ≠ Coin | ✅ | ✅ | ✅ |

---

## Key Insights

### 1. The design trade-off is real
Every broker that unified their app sacrificed trading depth. Groww's charting is inadequate for active traders. Angel One's F&O tooling is adequate but not professional-grade. **Zerodha's competitive moat is Kite's professional-grade trading tools** — this must not be compromised.

### 2. The fix is surgical, not a rebrand
The solution is **not** to redesign Kite into Groww. It is to **integrate Coin's MF functionality as a tab within Kite's existing Portfolio screen**. The bottom nav stays identical. The charting, F&O, and order-placement screens are untouched.

### 3. Global search is the single highest-leverage feature
The recognition-to-recall failure happens at the **search step**: users type a fund name in Kite, find the fund, and then get sent to Coin to invest. A unified global search eliminates this entirely without requiring any structural app changes.

---

## Solution

### What changes

| Component | Change |
|-----------|--------|
| **Portfolio bottom tab** | Gains two new sub-tabs: "Overview" and "Mutual Funds" (existing "Holdings" preserved) |
| **Portfolio Overview tab** | NEW — combined equity + MF current value, total P&L, asset allocation chart |
| **Mutual Funds tab** | NEW — all MF holdings, SIP status, next deduction date, invest CTA |
| **Global search** | ENHANCED — returns grouped results: Stocks section + Mutual Funds section |
| **Invest flow (MF)** | NEW — full SIP + lumpsum invest from within Kite, zero redirect to Coin |

### What does NOT change

- Watchlist (stocks, ETFs, F&O) — identical to today
- Charting — identical to today
- Order placement (buy/sell, GTT, bracket, cover) — identical to today
- F&O screens — identical to today
- Bottom navigation layout — identical to today
- Coin app — continues to exist and function

---

## Wireframes

Three annotated wireframe screens (see attached PNG exports or Figma file):

### Screen 1: Unified Search
```
┌─────────────────────────────────┐
│ 🔍 Search stocks and funds      │
├─────────────────────────────────┤
│ STOCKS                          │
│ HDFCBANK    ₹1,346.80 ▲ +0.09% │
│ HDFCAMC     ₹2,792.40 ▲ +4.89% │
├─────────────────────────────────┤
│ MUTUAL FUNDS                    │
│ HDFC Flexi Cap · Direct Growth  │
│                         [Invest]│
│ HDFC Mid-Cap · Direct Growth    │
│                         [Invest]│
└─────────────────────────────────┘
Annotation: One search bar → two asset classes.
No app switch. No prior knowledge required.
```

### Screen 2: Portfolio Overview (new tab)
```
┌─────────────────────────────────┐
│ [Overview] Holdings  Mutual Fds │
├─────────────────────────────────┤
│ Total Portfolio Value           │
│ ₹4,82,540                       │
│ +₹4,028  +0.84% today           │
├─────────────────────────────────┤
│ Asset Breakdown                 │
│ ████████████░░░░░ Equity 68%    │
│ ░░░░░░░░░░░░████░ MF 32%        │
├─────────────────────────────────┤
│ Equity Holdings    ₹3,28,450 →  │
│ Mutual Funds       ₹1,54,090 →  │
├─────────────────────────────────┤
│ Tax Summary (FY26): Est. LTCG   │
│ ₹12,400 · STCG ₹3,200  →       │
└─────────────────────────────────┘
Annotation: First time in Zerodha's history that
equity + MF wealth visible in one screen.
```

### Screen 3: Invest Flow (MF, inside Kite)
```
┌─────────────────────────────────┐
│ ← Parag Parikh Flexi Cap        │
│ Direct · Growth · 3Y: 19%/yr   │
├─────────────────────────────────┤
│ [  SIP  ]  One-time             │
│ Monthly Amount                  │
│ ₹ 2,000                         │
│ Deduction Date                  │
│ 10th of every month             │
├─────────────────────────────────┤
│ [    Start SIP →              ] │
│ No app switch needed — this     │
│ is Kite.                        │
└─────────────────────────────────┘
Annotation: Identical visual language to Kite.
User never leaves the app.
```

---

## Before / After

| Metric | Before (Zerodha) | After (Redesign) |
|--------|-----------------|-----------------|
| Screens to invest in stock + SIP | 14 | 7 |
| App switches required | 1 | 0 |
| Estimated time | ~5–6 min | ≤3 min |
| Portfolio screens | 2 (Kite + Coin) | 1 unified |
| Search systems | 2 separate | 1 global |
| Combined P&L visible | Never | Always |
| Kite trading tools | ✅ Working | ✅ Unchanged |

---

## PRD Summary

### Personas
- **Rohan, 28** — Active trader, uses F&O weekly, sets up monthly SIPs. Goal: MF tasks without leaving Kite.
- **Priya, 34** — SIP-only investor, 3 active funds. Goal: total savings view in one tap.
- **Kiran, 42** — Wealth builder, ₹15L+ across instruments. Goal: consolidated XIRR and tax summary.

### MoSCoW
**Must Have:** Unified Portfolio Overview, MF tab in Kite, invest from Kite (SIP + lumpsum), zero trading regressions, real-time P&L with NAV.

**Should Have:** Global search (stocks + MF), SIP management from Kite, asset allocation chart, tax summary, SIP push notifications.

**Could Have:** Cross-instrument watchlist, goal-based SIP wizard, consolidated statement export.

**Won't Have (v1):** Full Coin deprecation, NPS/FD/bonds integration, social trading.

### Edge Cases
- SIP mandate failure → proactive red banner + push notification with fix link
- Zero MF holdings → empty state with "Start your first SIP" CTA
- Coin account not linked → one-time OAuth-style linking prompt on first MF tab access
- NAV unavailable (holiday) → show previous day's value with clear "as of [date]" label

---

## Expected Metrics

| Metric | Baseline | 6-Month Target |
|--------|----------|----------------|
| Task completion rate (stock + SIP) | ~60% | ≥ 85% |
| Cross-product MF activation | 0% | +25% MF orders from Kite |
| Time-on-task | ~5–6 min | ≤ 3 min |
| Portfolio tab DAU | Low | +40% |
| NPS (30-day post-launch) | Baseline | +10 NPS points |

---

## Deliverables

```
zerodha-ux-audit/
├── zerodha_ux_audit.docx          # Heuristic table + Journey map + Competitive analysis + Problem statement
├── zerodha_prd.docx               # Full PRD: personas, user stories, MoSCoW, edge cases, KPIs, launch plan
├── zerodha_ux_redesign.pptx       # 10-slide presentation with wireframes and all deliverables
└── README.md                      # This file — case study summary
```

### What's inside the DOCX

| Section | Content |
|---------|---------|
| Problem Statement | Problem, root cause, user impact, hypothesis, KPIs |
| Heuristic Evaluation | All 10 Nielsen heuristics × Kite score + Coin score + observation + severity |
| User Journey Map | 14-step Zerodha flow vs 7-step Angel One flow, with screenshots |
| Competitive Analysis | 8 dimensions × 4 brokers (Zerodha, Angel One, Groww, Upstox) |
| PRD | Personas, user stories, MoSCoW, edge cases, tech notes, launch plan |

### What's inside the PPTX

| Slide | Content |
|-------|---------|
| 1 | Cover — problem framing with live screenshots |
| 2 | Problem Statement — 4 impact areas |
| 3 | Heuristic Evaluation table |
| 4 | User Journey Map — step-by-step comparison |
| 5 | Screenshot Evidence — 6 app screenshots annotated |
| 6 | Competitive Analysis matrix |
| 7 | Redesign Proposal — 3 annotated phone wireframes |
| 8 | Before / After comparison |
| 9 | PRD Summary — MoSCoW + KPI table |
| 10 | Closing — design philosophy |

---

## Tools Used

- **UX Research:** Nielsen Heuristic Framework, User Journey Mapping, Competitive Analysis
- **Evidence:** Live screenshots captured from Zerodha Kite, Coin, and Angel One production apps (April 2026)
- **Documentation:** docx-js (Word documents), PptxGenJS (presentation)
- **Design Methodology:** Jobs-to-be-Done, Heuristic Evaluation, Before/After flow comparison

---

## Design Philosophy

> *"Zerodha doesn't need to become Groww. It needs to absorb Coin into Kite's existing shell — additive, not disruptive. The best redesign is the one where active traders don't even notice anything changed, but SIP investors suddenly find everything they need."*

The integration preserves Zerodha's core competitive differentiation (Kite's professional-grade trading tools) while eliminating the single biggest UX complaint from non-trader investors: the two-app tax.

---

*April 2026 · UX Research & Design · Zerodha Kite + Coin Case Study*
