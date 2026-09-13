# Turkey — Channel Review

**Period:** August (actuals)
**Sources:** Monthly channel/volume tracker (status, cascade line, volume) + multi-GEO rate card (commission/settlement terms), merged by channel name. Only channels tracked as active in the volume tracker are included — see `README.md` for scope rationale.

---

## Channels

| Channel | Vertical | Status | Cascade line | AFU | Daily vol (USDT) | Monthly vol (USDT) | PayIn | PayOut | Settlement | FX source | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|
| BigIdea | Betting | Live | L1 | Yes | 0 | 0 | 4.75% | 0.5% | T+0 +2% | Binance | Traffic not launched despite Live/AFU status |
| Prime | Betting | Live | L1 | Yes | 1,080 | 30,000 | 5.2% | 1% | T+1 +2% | Binance | Carries 93% of Turkey's tracked volume; –$3 fee if settlement <5,000 USDT |
| Favori | Betting | Live | L1 | Yes | 0 | 0 | 5% | 0% | T+0 +3% | Doviz.com | Traffic not launched; min settlement 2,000 USDT |
| Corytech | Betting | Live | L1 | Yes | 0 | 0 | 5% | 0.5% | T+0 +3% | Binance | Traffic not launched |
| E4A | Betting | Live | L2 | Yes | 81 | 2,100 | 5.5–7.5% | 2% | T+1 +2% | Binance | Only channel with tracked conversion data: 50–70% (FTD/STD) |
| Astrum | Betting | Live | L2 | Yes | 0 | 0 | 5.5% | 1.5% | T+0 +1% | Binance | Traffic not launched |
| Astrum | Forex | Live | L1 | Yes | 0 | 0 | 5.5% | 1.5% | T+0 +1% | Binance | Same channel/rate as Astrum-Betting; Forex traffic not launched |
| Corytech | Adult | Terminal being issued | L1 | No | N/A | N/A | 6% | N/A | T+1 +3.5% | Binance | Not yet enabled in AFU; min settlement 5,000 USDT |

Raw extract: [`data/turkey_channels_august.csv`](../data/turkey_channels_august.csv), [`data/turkey_rate_card.csv`](../data/turkey_rate_card.csv)

---

## August review notes (as recorded by the payments team)

> In August we updated offers across all channels and rebuilt cascades. Rates were lowered on Prime; BigIdea was re-enabled at a lower rate. Two new channels were added — Corytech and Favori. A new vertical (Adult) was opened on Corytech. Priority for September: grow traffic on the already-integrated Betting channels and launch traffic under Adult and Forex.

## What this actually shows

- **6 channels, 8 tracked lines, but only 2 are carrying real volume** — Prime and E4A. Everything else is Live and AFU-approved but sitting at zero.
- **The cheapest channel (BigIdea, 4.75%) is one of the idle ones.** The channel carrying nearly all the volume (Prime) is priced 0.45 points above it. See `docs/cost_analysis.md` for what that costs in practice.
- **Corytech-Adult is the one line not yet fully switched on** (AFU = No) — it's the most expensive line in the table (6% PayIn, 3.5% settlement) and also the newest vertical, so cost here reflects opening a new line of business rather than routing inefficiency.
- **E4A is the only channel with conversion data on file, and it's weak** (50–70%) relative to what a Betting channel should clear — flagged for follow-up in `docs/payment_cascades.md`.

---

## September (per tracker)

The tracker rolls the same 8 lines forward into September with all data columns blank, plus 3 open "New channel" slots. No targets have been filled in yet. See `docs/roadmap_sept_oct_2026.md` — this is tracked as **pending**, not assumed.
