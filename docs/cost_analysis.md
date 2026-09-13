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

**Important caveat, per the payments team:** this isn't simply a case of routing inefficiency to fix by pushing volume onto the cheapest channel. **Prime's settlement limits are lower and more stable than BigIdea's or any other live Turkey channel's**, and Incas' Turkey traffic is small-ticket by design — that traffic profile prioritises low, stable limits over the lowest headline rate. That's consistent with the actual operating cascade (see `docs/turkey_channel_review.md`): BigIdea sits at L1 but most real volume lands on Prime at L2, because Prime's limits fit the traffic. The 9% cost gap above is still real and worth tracking, but it should be read as **the cost of limits/stability fit**, not as neglect of a cheaper option.

Two more cost notes from Turkey:
- **Corytech-Adult (6% PayIn, 3.5% settlement)** is the single most expensive line tracked, but it's also the only Adult-vertical channel and isn't yet switched on in AFU — this is the cost of opening a new vertical, not routing inefficiency.
- **Prime carries a $3 flat penalty on settlements under 5,000 USDT** — worth watching if settlement batching changes.

---

## China — no reallocation opportunity yet, but the same idle-cheap shape on the payin side

China's real volume is 100% on one channel — TCL's Alipay/WeChat payout leg, 2.7%, $1.5M/month, "very stable." There's no cheaper *confirmed* live payout channel to compare it against today (Fastsecurepay's on-file rate is for the wrong direction — see `docs/data_gaps.md` — so it can't be treated as a confirmed alternative).

On the payin side, all three tracked channels (TCL, Fastsecurepay, Moneystery) are at **zero volume** — pre-launch, not yet a cost-vs-volume mismatch the way Turkey's is. But the same shape shows up in the rate card: **TCL payin, at 4.5% with 90% conversion, is the cheapest and best-tested option on file, and it's the one sitting idle.** Moneystery (9.5%) is markedly more expensive, but it's the only Adult-vertical channel — again, vertical cost, not inefficiency.

**Takeaway across both GEOs:** in Turkey and China alike, the cheapest, already-approved, best-tested channel (BigIdea / TCL-payin) is the one not carrying traffic. That's the pattern worth fixing operationally before anything else in this pack.

---

## The new China channels (Sept–Oct plan) — one confirmed cheaper, one pending

Two new Alipay payout channels are planned for Sept–Oct.

**Channel 1 — confirmed.** Priced at **HTX P2P + 3%** (nominal). TCL's real all-in cost is **2.7% payout + 0.2% agent fee + xe.com reference (+0%) = 2.9% all-in**. On the surface the two nominal figures (~3% vs. 2.9%) look close — and that's expected, not a red flag: the HTX +3% is a **single fee blended directly against the live exchange rate**, unlike TCL's structure, which stacks a payout fee, an agent fee, and a separate xe.com reference rate. Because of that, the visible nominal margins aren't a like-for-like comparison. Per the payments team, once the live HTX P2P rate is accounted for, the true all-in cost comes out **roughly 4 percentage points lower** than TCL's.

This 4pp figure is provided directly by the payments team, not derived from either source spreadsheet — it depends on live market spread that isn't in either file, so it's recorded here as a provided input rather than something this pack independently verified. See `docs/data_gaps.md`.

**Channel 2 — candidate, rate not yet confirmed.** Fills the tracker's second open "New channel" slot for September. Not cost-ranked until a rate is confirmed.

**Proposed cascade position:** TCL, the confirmed HTX channel, and the second candidate all sit at L1 — TCL kept for its proven stability and volume history, the HTX channel absorbing the cost-sensitive share once it finishes integration, the second channel joining once its rate is confirmed.

**Growth targets tied to this change** (as provided, by end of October):

| Metric | August | Target |
|---|---|---|
| Payout volume | 1,500,000 USDT/mo | 3,000,000 USDT/mo |
| Payin volume | 0 | ~50,000 USDT/day (≈1,500,000 USDT/mo) |
| Blended margin | 0.1% | 4–5% |

The margin jump from 0.1% to 4–5% is attributed to the cheaper payout channel absorbing a growing share of a larger volume base — again, a provided target, not a figure this pack calculates independently.

---

## Cross-GEO comparison and profitability projection

See `docs/geo_progress_comparison.md` for the side-by-side Turkey vs. China progress table and the per-$100k cost sensitivity used above, applied consistently across both GEOs.
