# Turkey — Channel Review

**Period:** August (actuals)
**Sources:** Monthly channel/volume tracker (status, cascade line, volume) + multi-GEO rate card (commission/settlement terms), merged by channel name. Only channels tracked as active in the volume tracker are included — see `README.md` for scope rationale.

---

## Channels

| Channel | Vertical | Status | Cascade line | AFU | Daily vol (USDT) | Monthly vol (USDT) | PayIn | PayOut | Settlement | FX source | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Payinextra | Betting | Discontinued early August | L1 | Yes | N/A | 30,000 | 4.5% | 0.5% | T+0 +2.5% | Doviz.com | Carried the majority of Turkey's volume while active, on low fee and low, stable limits; stopped working in early August |
| BigIdea | Betting | Live | L1 | Yes | 0 | 0 | 4.75% | 0.5% | T+0 +2% | Binance | Traffic not launched despite Live/AFU status |
| Prime | Betting | Live | L1 | Yes | 1,080 | 30,000 | 5.2% | 1% | T+1 +2% | Binance | Absorbed the volume after Payinextra stopped working |
| Favori | Betting | Live | L1 | Yes | 0 | 0 | 5% | 0% | T+0 +3% | Doviz.com | Traffic not launched; min settlement 2,000 USDT |
| Corytech | Betting | Live | L1 | Yes | 0 | 0 | 5% | 0.5% | T+0 +3% | Binance | Traffic not launched |
| E4A | Betting | Live | L2 | Yes | 81 | 2,100 | 5.5–7.5% | 2% | T+1 +2% | Binance | Only channel with tracked conversion data: 50–70% (FTD/STD) |
| Astrum | Betting | Live | L2 | Yes | 0 | 0 | 5.5% | 1.5% | T+0 +1% | Binance | Traffic not launched |
| Astrum | Forex | Live | L1 | Yes | 0 | 0 | 5.5% | 1.5% | T+0 +1% | Binance | Same channel/rate as Astrum-Betting; Forex traffic not launched |
| Corytech | Adult | Terminal being issued | L1 | No | N/A | N/A | 6% | N/A | T+1 +3.5% | Binance | Not yet enabled in AFU; min settlement 5,000 USDT |

Raw extract: [`data/turkey_channels_august.csv`](../data/turkey_channels_august.csv), [`data/turkey_rate_card.csv`](../data/turkey_rate_card.csv)

---

## Settlement limits

Active channels currently configured in the system. Values are unchanged between the August and September tabs on file.

| Channel | Balance type | Settlement limit (TRY) | Deposit | Limit set in AFU |
|---|---|---|---|---|
| BigIdea | Fiat | 148,000 | N/A | Yes |
| Prime | Fiat | 148,000 | N/A | Yes |
| Corytech | Fiat | 148,000 | N/A | Yes |
| E4A | Fiat | 148,000 | N/A | Yes |
| Astrum | Fiat | 148,000 | N/A | Yes |

"Limit set in AFU" here is a distinct field from the channel-level AFU status used elsewhere in this doc (e.g. Corytech-Adult's "not yet enabled in AFU") — it specifically tracks whether the settlement limit itself has been configured in AFU. All five active channels have their limit set in AFU.

Raw extract: [`data/turkey_settlement_limits.csv`](../data/turkey_settlement_limits.csv)

---

## August review notes (as recorded by the payments team)

> In August we updated offers across all channels and rebuilt cascades. Rates were lowered on Prime; BigIdea was re-enabled at a lower rate. Two new channels were added — Corytech and Favori. A new vertical (Adult) was opened on Corytech. Priority for September: grow traffic on the already-integrated Betting channels and launch traffic under Adult and Forex.

## What this actually shows

- **7 channels tracked, but only 3 carried real volume** — Payinextra (while it worked), Prime, and E4A. Everything else is Live and AFU-approved but sitting at zero.
- **Payinextra was the cheapest channel on file (4.5%) and carried effectively all of Turkey's volume while it was active** — low fee combined with low, stable limits made it the natural home for small-ticket traffic. It stopped working in early August.
- **After Payinextra stopped, Prime absorbed nearly all of that volume instead** — not because it's the cheapest (5.2%, above BigIdea's 4.75%), but for the same reason Payinextra worked: low, stable settlement limits fit to small-ticket traffic. BigIdea, still Live and AFU-approved throughout, never picked up this volume despite being cheaper than Prime — limits, not rate alone, determine where volume actually lands. See `docs/cost_analysis.md`.
- **Corytech-Adult is the one line not yet fully switched on** (AFU = No) — it's the most expensive line in the table (6% PayIn, 3.5% settlement) and also the newest vertical, so cost here reflects opening a new line of business rather than routing inefficiency.
- **E4A is the only channel with conversion data on file, and it's weak** (50–70%) relative to what a Betting channel should clear — flagged for follow-up in `docs/payment_cascades.md`.

## The actual operating cascade (August)

The tracker's raw L1/L2 tags don't reflect how the cascade is actually run day to day. As confirmed by the payments team, the real order is:

| Tier | Channel(s) |
|---|---|
| L1 | Payinextra (discontinued early August), BigIdea |
| L2 | Corytech, **Prime** |
| L3 | Favori, E4A, Astrum |

While Payinextra was active it carried the bulk of L1 volume; after it stopped, traffic fell through to Prime at L2. Full cascade diagrams (current and proposed) are in `docs/payment_cascades.md`.

---

## September–October 2026 (plan)

Payinextra does not exist for this period — it's discontinued. Confirmed changes for this period, sorted cheapest first:

| Channel | PayIn | Limits PayIn | Notes |
|---|---|---|---|
| Continental (new) | 4.5% | 500 | Confirmed for L1 |
| BnPay (new) | 4.5% | 500 | Confirmed for L1 |
| Astrum | **4.5%** (renegotiated from 5.5%) | 500 | Moves into L1, ahead of BigIdea |
| BigIdea | 4.75% | — | idle, unchanged |
| Corytech (Betting) | 5% | — | unchanged |
| Prime | 5.2% | — | unchanged |
| E4A | 5.5% (base) | — | conv. 50–70% unchanged, still flagged |

Continental and BnPay are confirmed at 4.5% PayIn with a 500 PayIn limit for cascade placement — full rate-card terms (max limits, settlement, FX source) aren't in the standard rate card yet, see `docs/data_gaps.md`.

**Desired cascade, September–October:**

| Tier | Channel(s) |
|---|---|
| L1 | Continental (new, limits PayIn 500), BnPay (new, limits PayIn 500), Astrum (4.5%, renegotiated, limits PayIn 500) |
| L2 | BigIdea (4.75%, idle), Corytech, Prime |
| L3 | the rest |

**Finding:** a strong L1 — three channels at 4.5% with stable, low limits (PayIn 500) — ahead of BigIdea and everything else in the August cascade. This effectively replaces the low-cost, low-limit capacity Payinextra provided in August before it stopped working — at the same 4.5% rate, but now spread across three channels instead of depending on one.
