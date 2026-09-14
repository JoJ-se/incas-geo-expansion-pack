# Turkey vs. China — Progress & Cost Comparison

This section puts the two GEOs side by side: what's actually running, what it costs, and how much more profitable a cost-optimised routing would be — using only real, current numbers.

---

## Part 1 — Progress tracking, side by side

| | Turkey | China |
|---|---|---|
| Active channels tracked | 7 (incl. 1 discontinued) | 3 |
| Tracked lines (incl. verticals/methods) | 9 | 7 |
| Live monthly volume | 62,100 USDT (Betting only) | 1,500,000 USDT (payout only) |
| Channels/lines carrying real volume | 3 of 9 (Payinextra while active, Prime, E4A) | 1 of 7 (TCL payout) |
| Live but at zero volume | 5 of 9 (plus Corytech-Adult not yet enabled; Payinextra now discontinued) | 5 of 7 (all payin lines + TCL corporate/WeChat/Adult in integration) |
| Cheapest channel | Payinextra, 4.5% — **discontinued early August**; BigIdea, 4.75%, cheapest still-available option — **idle** | TCL payin, 4.5% — **idle (pre-launch)** |
| Channel carrying the volume | Payinextra (while active), then Prime (5.2%) after it stopped | TCL payout, 2.7% PayOut |
| Sept–Oct 2026 plan | **Cascade confirmed** (Continental, BnPay, renegotiated Astrum — all 4.5%, replacing Payinextra's rate); volume targets still pending | **Confirmed** — new payout channel (~4pp cheaper) plus volume/margin targets |

**Reading this table:** Turkey's August is a real-world demonstration, not a hypothesis. Payinextra — the cheapest channel on file — carried effectively all of Turkey's volume while it worked, on low fee and low, stable limits. When it stopped working in early August, Prime absorbed nearly all of that volume instead, despite being priced above BigIdea — again because of its limits, not its rate. BigIdea, cheaper than Prime and Live the whole month, never picked up the volume either time. The Sept–Oct plan responds directly to this: not by forcing volume onto BigIdea, but by adding three channels (Continental, BnPay, a renegotiated Astrum) at exactly Payinextra's old rate (4.5%) with matching low, stable limits — replacing the lost capacity with three channels instead of one. China's shape is simpler: the payin side is entirely pre-launch, so there's no live trade-off yet — but the confirmed Sept–Oct payout channel shows the same principle in reverse: a cheaper channel joining the proven one at L1, not replacing it.

---

## Part 2 — Cost comparison & profitability projection

### Turkey: the August gap, and what Sept–Oct actually fixes it with

| | August blended cost | Sept–Oct L1 (Continental, BnPay, Astrum) | Delta |
|---|---|---|---|
| PayIn, Betting | 4.87% (Payinextra/Prime/E4A weighted) | 4.5% | **–0.37pp (–7.6% relative, ≈$231/month at today's volume)** |

This delta is the same size as the gap between August's blended cost and Payinextra's own rate (see `docs/cost_analysis.md`) — because the Sept–Oct L1 tier is priced at exactly the rate Payinextra offered before it stopped working. This isn't a "route to the cheapest idle channel" scenario: Continental, BnPay, and the renegotiated Astrum are cheap **and** expected to carry stable, low limits suited to Turkey's small-ticket traffic — the same property that made Payinextra (and then Prime) the practical volume carriers in August. This is a real, confirmed cascade change; the one piece still missing is a volume target to size the full dollar impact at Sept–Oct scale.

### China: confirmed, with the full picture now available

| | August | Sept–Oct target |
|---|---|---|
| Payout cost (all-in) | TCL, 2.9% | New channel ~4pp cheaper, alongside TCL at L1 |
| Payout volume | 1,500,000 USDT/mo | 3,000,000 USDT/mo |
| Payin volume | 0 (pre-launch) | ~50,000 USDT/day (≈1,500,000 USDT/mo) |
| Blended margin | 0.1% | 4–5% |

The cost, volume, and margin figures for Sept–Oct are provided directly by the payments team (see `docs/data_gaps.md` for provenance) rather than derived independently in this pack — they're treated as confirmed inputs, not projections this document calculates.

### China payin, once it launches

Once TCL, Fastsecurepay, and Moneystery start carrying real payin volume, the same logic applies: TCL (4.5%, 90% conversion) is the clear default over Moneystery (9.5%, Adult-only) — this is the core recommendation already carried into `docs/payment_cascades.md`.

---

## Bottom line

Turkey's fix isn't "push volume to the cheapest channel" — August already proved the pattern twice in real life: Payinextra carried the volume while it was cheap and stable, then Prime took over for the same limits-fit reason once Payinextra stopped, and BigIdea (cheaper than Prime) never got the traffic either time. The Sept–Oct plan responds by adding channels that are both cheap *and* fit that stable-limit profile, at exactly the rate the departed channel offered. China's fix is more direct: a new payout channel that's genuinely cheaper once live FX is accounted for, running alongside the proven TCL channel rather than replacing it, with confirmed volume and margin targets for the ramp to end of October.
