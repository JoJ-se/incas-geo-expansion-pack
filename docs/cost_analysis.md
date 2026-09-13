# Cost Analysis — Turkey & China

Every figure below is computed from the tables in `docs/turkey_channel_review.md` and `docs/china_channel_review.md`. Where a calculation is a scenario rather than a recorded fact (i.e. "what would it cost if..."), that's labeled explicitly.

---

## Turkey — the idle-cheap pattern

Turkey's tracked Betting volume in August is small (32,100 USDT/month total) and concentrated in two channels:

| Channel | PayIn | Monthly volume | Share of total volume |
|---|---|---|---|
| Prime | 5.2% | 30,000 USDT | 93.5% |
| E4A | 5.5–7.5% (using 5.5% base) | 2,100 USDT | 6.5% |

**Current blended PayIn cost** (volume-weighted across the two channels actually carrying traffic):

```
(30,000 × 5.2%) + (2,100 × 5.5%)
──────────────────────────────── = 5.22%
        32,100
```

**Scenario — routed through the cheapest idle Live channel instead:** BigIdea is Live, AFU-approved, and priced at 4.75% — but carries zero volume. If the same 32,100 USDT/month were routed through BigIdea instead of the current mix:

- Blended cost: **4.75%** vs. today's 5.22% → **0.47 percentage points, a ~9% relative reduction**
- In dollar terms at *today's* volume: **≈ $151/month** saved
- Scaled per $100,000 of monthly volume (since Turkey's real volume is still tiny and Sept–Oct targets aren't set yet): **≈ $470/month saved per $100k of volume routed through BigIdea instead of the current mix**

This is the headline Turkey finding: **the cost problem isn't that any single channel is priced unreasonably — it's that the cheapest approved channel is the one with no traffic on it.** The fix is operational (route more traffic to BigiIdea, investigate why it isn't launched) rather than a renegotiation.

Two more cost notes from Turkey:
- **Corytech-Adult (6% PayIn, 3.5% settlement)** is the single most expensive line tracked, but it's also the only Adult-vertical channel and isn't yet switched on in AFU — this is the cost of opening a new vertical, not routing inefficiency.
- **Prime carries a $3 flat penalty on settlements under 5,000 USDT** — worth watching if settlement batching changes.

---

## China — no reallocation opportunity yet, but the same idle-cheap shape on the payin side

China's real volume is 100% on one channel — TCL's Alipay/WeChat payout leg, 2.7%, $1.5M/month, "very stable." There's no cheaper *confirmed* live payout channel to compare it against today (Fastsecurepay's on-file rate is for the wrong direction — see `docs/data_gaps.md` — so it can't be treated as a confirmed alternative).

On the payin side, all three tracked channels (TCL, Fastsecurepay, Moneystery) are at **zero volume** — pre-launch, not yet a cost-vs-volume mismatch the way Turkey's is. But the same shape shows up in the rate card: **TCL payin, at 4.5% with 90% conversion, is the cheapest and best-tested option on file, and it's the one sitting idle.** Moneystery (9.5%) is markedly more expensive, but it's the only Adult-vertical channel — again, vertical cost, not inefficiency.

**Takeaway across both GEOs:** in Turkey and China alike, the cheapest, already-approved, best-tested channel (BigIdea / TCL-payin) is the one not carrying traffic. That's the pattern worth fixing operationally before anything else in this pack.

---

## The new China channel (Sept–Oct plan) — is it actually cheaper?

The confirmed Sept–Oct addition is a new Alipay payout channel priced at **HTX P2P + 3%**. Compared to TCL's current effective payout margin (2.7%), the nominal add-on here is *higher*, not lower. Two ways to read this:

1. If HTX's underlying P2P quote for USDT→CNY is meaningfully better than the xe.com reference rate TCL uses, the all-in cost to Incas could still come out ahead of 2.7% — but that depends on live market spread, which isn't in either source file.
2. If it isn't, this channel is better framed as **redundancy/capacity** for the payout leg (reducing single-channel dependency on TCL) rather than a cost win.

Flagged in `docs/roadmap_sept_oct_2026.md` as "confirmed, cost impact to verify against live HTX quotes" rather than assumed to be an improvement.

---

## Cross-GEO comparison and profitability projection

See `docs/geo_progress_comparison.md` for the side-by-side Turkey vs. China progress table and the per-$100k cost sensitivity used above, applied consistently across both GEOs.
