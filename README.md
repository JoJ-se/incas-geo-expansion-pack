# incas-geo-expansion-pack

## Overview

This repository is Incas' internal review pack for GEO development on **China** and **Turkey**. It documents the current state of payment channels in both markets — integration status, live volume, and cost — and lays out how the payment cascades in each market should be rebuilt with cost (weighted by conversion rate, where known) as the primary ordering factor.

It was put together to give a single, visual, data-backed answer to: *what do we run today, what does it cost, why does volume not match cost, and what changes for September–October 2026.*

---

## Scope

- **GEOs covered:** China and Turkey only.
- **Channels covered:** only channels actively tracked in the internal monthly channel/volume tracker (i.e. channels with a real integration status and cascade line as of August). Channels that exist only as rate-card candidates — quoted, in negotiation, paused, or archived, and never actually carried traffic — are intentionally excluded from the review, so every number in this pack maps to something actually running.
- **Not covered:** other GEOs in the wider rate-card workbook (CIS, LatAm, MENA, Africa, etc.), cross-border/Vietnam pilots, regional event calendars, and internal SOP documents — all out of scope for this pack by design.

---

## Data sources

Everything in this pack is derived from two internal spreadsheets, cross-referenced against each other — no figures are invented or estimated:

1. **Monthly channel/volume tracker** — per-GEO, per-vertical channel status, cascade line (L1/L2), AFU status, daily/monthly volume, and the payments team's own review notes. This is the source of truth for *which channels are active* and *how much volume they carry*.
2. **Multi-GEO rate card** — the full commission/settlement rate sheet (PayIn %, PayOut %, settlement terms, FX source, conversion rate where tracked). Used only for the channels confirmed active in source (1); rows are matched by channel name and payment method.

Where the two sources disagree or a rate/conversion figure simply isn't tracked yet, that gap is recorded explicitly in `docs/data_gaps.md` rather than filled in with an assumption.

---

## Repository Contents

```
incas-geo-expansion-pack/
├── README.md                          # This file
├── index.html                         # Visual dashboard — charts, status, cascades
├── docs/
│   ├── turkey_channel_review.md       # Turkey: channels, status, volume, cost, review notes
│   ├── china_channel_review.md        # China: channels, status, volume, cost, review notes
│   ├── cost_analysis.md               # Cost findings — cheapest vs. loaded, idle-cheap channels
│   ├── payment_cascades.md            # Current vs. cost-optimised cascades, per GEO/vertical
│   ├── geo_progress_comparison.md     # Turkey vs. China — progress, cost, profitability projection
│   ├── roadmap_sept_oct_2026.md       # Forward plan — confirmed items only, rest marked pending
│   └── data_gaps.md                   # Open discrepancies and missing figures, tracked explicitly
└── data/
    ├── turkey_channels_august.csv     # Raw extract: Turkey status/volume/cascade line
    ├── china_channels_august.csv      # Raw extract: China status/volume/cascade line
    ├── turkey_rate_card.csv           # Raw extract: Turkey PayIn/PayOut/settlement rates
    └── china_rate_card.csv            # Raw extract: China PayIn/PayOut/settlement rates
```

---

## How to read this pack

- Start with **`index.html`** for the visual summary — channel cost comparison, live-vs-idle volume, and the cascade diagrams.
- **`docs/turkey_channel_review.md`** and **`docs/china_channel_review.md`** are the detailed per-GEO tables behind the dashboard.
- **`docs/cost_analysis.md`** is the "why does this cost so much" narrative — which channels are cheapest, which carry the volume, and where those two things don't line up.
- **`docs/payment_cascades.md`** is the largest document in the pack: it shows the current cascade lines as tracked today, and proposes a rebuilt cascade ordered by cost with a conversion-rate check where that data exists.
- **`docs/geo_progress_comparison.md`** puts Turkey and China side by side — active channels, live volume, blended cost, and the profitability gain from routing to the cheapest proven channel, computed from real volume rather than a projected target.
- **`docs/roadmap_sept_oct_2026.md`** only contains what's actually been confirmed for September–October 2026 (currently: one new China channel). Everything else is explicitly marked pending rather than guessed.
- **`docs/data_gaps.md`** lists every place the two source spreadsheets didn't agree, or a figure wasn't available — check here before treating any number as final.
- **`data/*.csv`** are the raw structured extracts behind every table in the docs, so any figure can be traced back to source.

---

## Status

| Item | Status |
|---|---|
| Turkey channel review (August) | Complete |
| China channel review (August) | Complete |
| Cost analysis | Complete |
| Payment cascades (current + proposed) | Complete |
| Turkey vs. China progress &amp; profitability comparison | Complete |
| China Sept–Oct 2026 plan | Confirmed — new payout channel, volume &amp; margin targets |
| Turkey Sept–Oct 2026 plan | Cascade confirmed (Continental, BnPay, renegotiated Astrum); volume targets still pending |

---

## Maintenance Ownership

| Role | Responsibility |
|---|---|
| Payments Team | Maintains channel/volume tracker and rate card; source of truth for all figures in this pack |
| Process/Team Lead | Maintains this repository, approves structural changes, resolves items in `data_gaps.md` |

---

## Internal use only

This repository contains real commission rates, partner names, and volume figures. It is private and should not be shared outside Incas without approval.
