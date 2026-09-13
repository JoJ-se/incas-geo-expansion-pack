# Turkey vs. China — Progress & Cost Comparison

This section puts the two GEOs side by side: what's actually running, what it costs, and how much more profitable a cost-optimised routing would be — using only real, current numbers. Where a genuine future volume target doesn't exist yet (Turkey's September/October plan), this section uses a **per-$100,000-of-volume sensitivity** instead of inventing a projection, so the numbers stay honest and still scale cleanly once real targets land.

---

## Part 1 — Progress tracking, side by side

| | Turkey | China |
|---|---|---|
| Active channels tracked | 6 | 3 |
| Tracked lines (incl. verticals/methods) | 8 | 7 |
| Live monthly volume | 32,100 USDT (Betting only) | 1,500,000 USDT (payout only) |
| Channels/lines carrying real volume | 2 of 8 (Prime, E4A) | 1 of 7 (TCL payout) |
| Live but at zero volume | 5 of 8 | 5 of 7 (all payin lines + TCL corporate/WeChat/Adult in integration) |
| Cheapest tracked channel | BigIdea, 4.75% PayIn — **idle** | TCL payin, 4.5% — **idle (pre-launch)** |
| Channel carrying the volume | Prime, 5.2% PayIn | TCL payout, 2.7% PayOut |
| Sept–Oct 2026 plan | **Pending** — no targets provided yet | **Partial** — 1 new payout channel confirmed (HTX P2P +3%) |

**Reading this table:** both GEOs show the identical shape — the cheapest, already-approved channel is not the one carrying traffic. Turkey's version of this costs real money today because Prime already has $30k/month running through it at a higher rate than the idle BigIdea. China's version hasn't cost anything yet because the whole payin side is still pre-launch — but it's the same routing decision waiting to be made correctly from day one, rather than corrected later.

---

## Part 2 — Cost comparison & profitability projection

### Turkey: measurable today

| | Current blended cost | Optimised (route to cheapest idle Live channel) | Delta |
|---|---|---|---|
| PayIn, Betting | 5.22% | 4.75% | **–0.47pp (–9% relative)** |
| $ impact at today's volume (32,100 USDT/mo) | — | — | **≈ $151/month** |
| $ impact per $100,000/month of volume | — | — | **≈ $470/month** |

This is a real, computable saving *right now* — it doesn't depend on any Sept–Oct target. It only requires shifting live traffic toward BigIdea instead of concentrating it on Prime. As Turkey's volume grows (once real Sept–Oct targets are set), this 9% relative gap compounds linearly with volume — e.g. at $500,000/month it's roughly $2,350/month, at $1,000,000/month roughly $4,700/month, all from routing alone, no rate renegotiation required.

### China: not yet measurable, one open question

China has no live reallocation opportunity today — TCL's payout leg is the only channel with real volume, and there's no confirmed cheaper live alternative to shift it to (see `docs/cost_analysis.md` on the Fastsecurepay direction mismatch). The one number worth tracking for profitability is the new HTX channel: its **+3% nominal margin is higher than TCL's current 2.7%**, so — unless the live HTX P2P quote undercuts TCL's xe.com reference — this channel should be read as **capacity/redundancy, not a cost improvement**. This is flagged as an open item to verify once the channel is live, not resolved as either a win or a cost in this pack.

### The one number that will matter most once China's payin side launches

Once TCL, Fastsecurepay, and Moneystery start carrying real payin volume, the same Turkey-style calculation becomes possible for China. Pre-positioning: if China's payin volume defaulted to TCL (4.5%, 90% conversion) instead of splitting evenly across all three tracked channels (blended ≈ 7% assuming an even split across TCL 4.5% / Moneystery 9.5% / Fastsecurepay unconfirmed), the same "route to the cheapest proven channel first" logic applies — this is the core recommendation carried into `docs/payment_cascades.md`.

---

## Bottom line

The profitability opportunity in this pack isn't found in cheaper rates — every live channel's rate is already fixed on file. It's found in **routing**: both GEOs have a proven, cheap, approved channel sitting idle while a costlier one (or, in China's case, an unlaunched niche one) does the work. Fixing that costs nothing to implement and is worth roughly 9% of PayIn cost in Turkey today, scaling directly with volume, with China positioned to show the same gain the moment its payin side goes live.
