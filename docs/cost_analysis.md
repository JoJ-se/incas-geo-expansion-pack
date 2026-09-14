# Cost Analysis — Turkey & China

Every figure below is computed from the tables in `docs/turkey_channel_review.md` and `docs/china_channel_review.md`. Where a calculation is a scenario rather than a recorded fact (i.e. "what would it cost if..."), that's labeled explicitly.

---

## Turkey — a real-world test of the low-fee/low-limits pattern

Turkey's tracked Betting volume in August totals 62,100 USDT/month, across three channels that actually carried traffic:

| Channel | PayIn | Monthly volume | Share of total volume |
|---|---|---|---|
| Payinextra (discontinued early August) | 4.5% | 30,000 USDT | 48.3% |
| Prime | 5.2% | 30,000 USDT | 48.3% |
| E4A | 5.5–7.5% (using 5.5% base) | 2,100 USDT | 3.4% |

**Current blended PayIn cost** (volume-weighted across all three):

```
(30,000 × 4.5%) + (30,000 × 5.2%) + (2,100 × 5.5%)
──────────────────────────────────────────────────── = 4.87%
                      62,100
```

**What actually happened, not a hypothetical:** Payinextra — the cheapest channel on file at 4.5% — carried effectively all of Turkey's volume while it was active, on a combination of low fee and low, stable settlement limits. It stopped working in early August. From that point, Prime absorbed nearly all of the volume instead — not because it's the cheapest (5.2%, above BigIdea's 4.75%), but for the same reason Payinextra worked: low, stable limits fit to small-ticket traffic. BigIdea, Live and AFU-approved the entire month, never picked up this volume despite being cheaper than Prime. This is direct, real evidence for the point raised in earlier drafts of this pack as a hypothesis: **limits, not rate alone, determine where volume actually lands** — it isn't just a plausible explanation for why Prime is used, it's what happened twice in one month with two different channels.

**Residual cost gap, now much smaller than previously modeled:** with Payinextra's real volume folded in, the blended cost (4.87%) sits close to BigIdea's rate (4.75%) — a gap of just **0.12pp (~2.5% relative, ≈$76/month at today's volume)**. Compared against Payinextra's own rate (4.5%, the cheapest actually achieved this month), the gap is **0.37pp (~7.6% relative, ≈$231/month)** — roughly the cost of not having Payinextra-equivalent coverage for the rest of the month once it stopped working.

**Forward link to Sept–Oct:** Payinextra does not exist for the September–October period. The plan's three new/renegotiated L1 channels — Continental, BnPay, and a renegotiated Astrum, all at 4.5% — sit at exactly the rate Payinextra offered, effectively replacing the capacity it carried, but spread across three channels instead of depending on one. See `docs/turkey_channel_review.md` and `docs/payment_cascades.md`.

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

**Proposed cascade position:** TCL, the confirmed HTX channel, and the second candidate all sit at L1 — TCL kept for its proven stability and volume history, the HTX channel absorbing the cost-sensitive share once it starts integration, the second channel joining once its rate is confirmed.

### Worked example — merchant Inwizo, 10,000 CNY payout

Provided by the payments team to illustrate the 4pp gap concretely. Rates on the day of the example: **xe.com 6.70, HTX 6.65** (CNY per USDT).

**Received from Inwizo (same in both scenarios):** 10,000 ÷ 6.70 = 1,492.54 USDT, plus a 3% fee (300 ÷ 6.70 = 44.78 USDT) = **1,537.31 USDT total received**.

**Scenario A — TCL:** cost to execute = 10,000 ÷ 6.70 = 1,492.54 USDT, plus the 2.7% payout fee (270 ÷ 6.70 = 40.30 USDT), plus the 0.2% agent fee (20 ÷ 6.70 = 2.99 USDT) = **1,535.83 USDT total spent**.
Margin = 1,537.31 − 1,535.83 = **1.48 USDT (~0.1%)**.

**Scenario B — new channel (HTX +3%, 0% fee, no agent fee):** the exchange rate itself carries the markup — 6.65 × 1.03 = 6.8495. Cost to execute = 10,000 ÷ 6.8495 = **1,459.96 USDT total spent**.
Margin = 1,537.31 − 1,459.96 = **77.35 USDT (~5.0%)**.

| | Received from Inwizo | Cost to execute | Margin (USDT) | Margin (%) |
|---|---|---|---|---|
| Scenario A — TCL | 1,537.31 | 1,535.83 | 1.48 | ~0.1% |
| Scenario B — New channel (HTX) | 1,537.31 | 1,459.96 | **77.35** | **~5.0%** |

**Finding:** switching to the new channel increases margin roughly **50×** under the same terms with Inwizo (0.1% vs. ~5.0%). The difference comes from the FX spread between xe.com (what Inwizo pays) and HTX (what Incas pays the channel), plus the absence of an agent fee on the new channel — TCL carries no FX spread since both sides use xe.com, and also carries the 0.2% agent fee the new channel doesn't. This example is provided by the payments team, using rates from one specific day — the exact margin will move with live xe.com/HTX spread, but the mechanism (FX-spread capture + no agent fee) is structural, not a one-off.

**Growth targets tied to this change** (as provided, by end of October):

| Metric | August | Target |
|---|---|---|
| Payout volume | 1,500,000 USDT/mo | 3,000,000 USDT/mo |
| Payin volume | 0 | ~50,000 USDT/day (≈1,500,000 USDT/mo) |
| Blended margin | 0.1% | 4–5% |

The margin jump from 0.1% to 4–5% is attributed to the cheaper payout channel absorbing a growing share of a larger volume base — again, a provided target, not a figure this pack calculates independently.

---

## Cross-GEO comparison and profitability projection

See `docs/geo_progress_comparison.md` for the side-by-side Turkey vs. China progress table, using the same real, actual-volume figures as above rather than a projected scenario.
