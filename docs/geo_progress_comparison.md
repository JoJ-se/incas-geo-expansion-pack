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
| Sept–Oct 2026 plan | **Cascade confirmed** (Continental, BnPay, renegotiated Astrum); volume targets still pending | **Confirmed** — new payout channel (~4pp cheaper) plus volume/margin targets |

**Reading this table:** in Turkey, the cheapest channel (BigIdea) is idle while Prime — priced 0.45pp higher — carries the real volume. Per the payments team, that's a deliberate trade-off: Prime's limits are lower and more stable, and Turkey's traffic is small-ticket by design, so it prioritises stable limits over the lowest rate. The Sept–Oct plan addresses this not by forcing volume onto BigIdea, but by adding new, genuinely cheap *and* stable-limit channels (Continental, BnPay, a renegotiated Astrum) at L1. China's shape is simpler: the payin side is entirely pre-launch, so there's no live trade-off yet — but the confirmed Sept–Oct payout channel shows the same principle in reverse: a cheaper channel joining the proven one at L1, not replacing it.

---

## Part 2 — Cost comparison & profitability projection

### Turkey: the August gap, and what Sept–Oct actually fixes it with

| | August blended cost | Sept–Oct L1 (Continental, BnPay, Astrum) | Delta |
|---|---|---|---|
| PayIn, Betting | 5.22% (Prime/E4A weighted) | 4.5% | **–0.72pp (–14% relative)** |

Unlike a simple "route to the cheapest idle channel" scenario, this isn't just cost-driven: Continental, BnPay, and the renegotiated Astrum are cheap **and** expected to carry stable, low limits suited to Turkey's small-ticket traffic — the same property that made Prime the practical volume carrier in August despite its higher rate. This is a real, confirmed cascade change; the one piece still missing is a volume target to size the dollar impact.

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

Turkey's fix isn't "push volume to the cheapest channel" — it's adding channels that are both cheap *and* fit the small-ticket, stable-limit traffic profile that made Prime the practical carrier despite its premium. China's fix is more direct: a new payout channel that's genuinely cheaper once live FX is accounted for, running alongside the proven TCL channel rather than replacing it, with confirmed volume and margin targets for the ramp to end of October.
