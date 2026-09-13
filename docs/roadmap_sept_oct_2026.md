# Roadmap — September–October 2026

This document only contains what has actually been confirmed. Anything not confirmed is marked **pending** rather than estimated — no invented volume targets or timelines appear here.

---

## China — confirmed

**New channel: Alipay payout via HTX P2P + 3%** (USDT → CNY)

| Field | Value |
|---|---|
| Method | Alipay payout |
| Cost | HTX P2P rate + 3% margin |
| Status | Confirmed for Sept–Oct 2026 |
| Cascade position (proposed) | L2 — see `docs/payment_cascades.md` |
| Cost impact | **Unverified.** Nominal +3% margin is higher than TCL's current effective payout margin (2.7%). Whether this is actually cheaper depends on the live HTX P2P quote vs. TCL's xe.com reference at settlement time — not yet checked. Treat as a capacity/redundancy addition until proven otherwise. |
| Volume target | Not provided |

This fills one of the two "New channel" placeholder slots in the tracker's September China tab. The second slot remains open.

---

## China — pending

- Second "New channel" slot (September tab) — no candidate confirmed yet.
- TCL's three in-integration lines (corporate payout, WeChat/UnionPay payin, Adult payin) — status is "in integration" with no rate published; not part of this roadmap until they clear that stage.
- Volume targets for Sept–Oct — not provided.

---

## Turkey — pending

The tracker's September tab rolls the same 8 channel/vertical lines forward from August with every data column blank, plus 3 open "New channel" slots. **No targets, no new channel candidates, and no cascade changes have been confirmed for Turkey's Sept–Oct plan as of this pack's last update.**

This is recorded here deliberately as a gap rather than filled with a projection — see `docs/geo_progress_comparison.md` for how the cost-optimisation numbers are framed (as per-$100k sensitivity) specifically so they don't depend on a target that doesn't exist yet.

**Action needed:** Turkey Sept–Oct volume targets and any new-channel plans should be provided and added here before this section can be marked complete.

---

## How to update this document

When new Sept–Oct data arrives:
1. Add it to the relevant GEO section above with a status (Confirmed / In progress / Candidate).
2. If it changes a cascade position, update `docs/payment_cascades.md` to match.
3. If it changes a cost comparison, update `docs/cost_analysis.md` and `docs/geo_progress_comparison.md`.
4. Move the corresponding line out of "pending" once resolved.
