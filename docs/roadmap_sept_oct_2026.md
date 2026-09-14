# Roadmap — September–October 2026

This document only contains what has actually been confirmed, or explicit targets as provided by the payments team. Anything not confirmed is marked **pending** rather than estimated — no invented volume targets or timelines appear here. Figures marked "provided target" are business inputs from the payments team, not calculations this pack derives independently.

---

## China — confirmed

**New channel: Alipay payout via HTX P2P + 3%** (USDT → CNY)

| Field | Value |
|---|---|
| Method | Alipay payout |
| Cost | HTX P2P rate + 3% margin (nominal) |
| Status | Confirmed for Sept–Oct 2026; starting integration |
| Cascade position | L1, alongside TCL — see `docs/payment_cascades.md` |
| Cost impact | **Confirmed cheaper, ~4 percentage points all-in**, versus TCL's 2.9% all-in (2.7% payout + 0.2% agent). Nominal margins look similar, but HTX's live P2P USDT→CNY rate runs more favourably than TCL's xe.com reference. This 4pp figure is provided directly by the payments team, not derived from either source spreadsheet — see `docs/data_gaps.md`. |

This fills one of the two "New channel" placeholder slots in the tracker's September China tab.

**Second new payout channel — candidate, rate not yet confirmed**

| Field | Value |
|---|---|
| Method | Alipay payout |
| Status | Candidate for Sept–Oct; fills the second "New channel" slot |
| Rate | Not yet confirmed |
| Cascade position | Pipeline — not cost-ranked until a rate is confirmed, see `docs/payment_cascades.md` |

**Growth targets, by end of October (provided targets):**

| Metric | August | Target |
|---|---|---|
| Payout volume | 1,500,000 USDT/mo | 3,000,000 USDT/mo |
| Payin volume | 0 | ~50,000 USDT/day (≈1,500,000 USDT/mo) |
| Blended margin | 0.1% | 4–5% |

**Additional confirmed Sept–Oct targets:**

| Item | Status | Note |
|---|---|---|
| Activate corporate payout / WeChat & UnionPay payout | Target | Once the corresponding integration clears |
| Growth volume for additional verticals — Adult, High Risk | Target | New vertical growth planned for Sept–Oct |
| Finish integration and launch WeChat Payin | Target | — |

---

## China — pending / in progress

- Corporate payout / WeChat & UnionPay payin — status is "in integration" with no rate published yet.
- Adult payin — status is "in integration" with no rate published yet; not part of the cost tables until it clears that stage.

---

## Turkey — confirmed

**Payinextra, the cheapest channel Turkey ran in August (4.5%), is discontinued and does not exist for this period.** Two new channels join a renegotiated Astrum at L1, at the same 4.5% rate, effectively replacing the capacity Payinextra carried before it stopped working:

| Channel | PayIn | Limits PayIn | Cascade position | Status |
|---|---|---|---|---|
| Continental (new) | 4.5% | 500 | L1 | Confirmed |
| BnPay (new) | 4.5% | 500 | L1 | Confirmed |
| Astrum | 4.5% (renegotiated from 5.5%) | 500 | Moves to L1, ahead of BigIdea | Confirmed |

Together these three form the proposed L1 tier for September–October — see `docs/payment_cascades.md` for the full cascade and `docs/turkey_channel_review.md` for the rate table.

## Turkey — pending

- Volume targets for Sept–Oct — not provided.
- Rate confirmation for Continental and BnPay in the standard rate card (currently confirmed only for cascade placement) — see `docs/data_gaps.md`.
- No changes confirmed yet for Forex or Adult verticals.

**Action needed:** Turkey Sept–Oct volume targets should be provided and added here before this section can be marked complete.

---

## How to update this document

When new Sept–Oct data arrives:
1. Add it to the relevant GEO section above with a status (Confirmed / In progress / Candidate / Provided target).
2. If it changes a cascade position, update `docs/payment_cascades.md` to match.
3. If it changes a cost comparison, update `docs/cost_analysis.md` and `docs/geo_progress_comparison.md`.
4. Move the corresponding line out of "pending" once resolved.
