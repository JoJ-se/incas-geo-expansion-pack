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
- **The cheapest channel (BigIdea, 4.75%) is one of the idle ones.** The channel carrying 93% of tracked volume (Prime) is priced 0.45pp above it — but this is not simple inefficiency: **Prime's settlement limits are lower and more stable than BigIdea's or any other live channel's**, and Turkey's traffic is small-ticket by design. That traffic prioritises low, stable limits over the lowest rate, which is why Prime carries the load despite sitting in L2 of the actual operating cascade (see below) rather than L1. See `docs/cost_analysis.md`.
- **Corytech-Adult is the one line not yet fully switched on** (AFU = No) — it's the most expensive line in the table (6% PayIn, 3.5% settlement) and also the newest vertical, so cost here reflects opening a new line of business rather than routing inefficiency.
- **E4A is the only channel with conversion data on file, and it's weak** (50–70%) relative to what a Betting channel should clear — flagged for follow-up in `docs/payment_cascades.md`.

## The actual operating cascade (August)

The tracker's raw L1/L2 tags don't reflect how the cascade is actually run day to day. As confirmed by the payments team, the real order is:

| Tier | Channel(s) |
|---|---|
| L1 | BigIdea |
| L2 | Corytech, **Prime** |
| L3 | Favori, E4A, Astrum |

Traffic is attempted on BigIdea first; most successful volume lands on Prime at L2, consistent with the limits/traffic-fit point above. Full cascade diagrams (current and proposed) are in `docs/payment_cascades.md`.

---

## September–October 2026 (plan)

Confirmed changes for this period:

| Channel | PayIn | Notes |
|---|---|---|
| BigIdea | 4.75% | idle, unchanged |
| Astrum | **4.5%** (renegotiated from 5.5%) | moves into the L1 tier |
| Corytech (Betting) | 5% | unchanged |
| Prime | 5.2% | unchanged |
| E4A | 5.5% (base) | conv. 50–70% unchanged, still flagged |

Plus two new channels confirmed for the cascade: **Continental** (4.5%) and **BnPay** (4.5%). Neither appears in this rate table because their PayIn figures were confirmed only for cascade placement, not yet added to the standard rate card — see `docs/data_gaps.md`.

**Desired cascade, September–October:**

| Tier | Channel(s) |
|---|---|
| L1 | Continental (new), BnPay (new), Astrum (4.5%, renegotiated) |
| L2 | Corytech, Prime |
| L3 | the rest |

**Finding:** a strong L1 — three channels at 4.5% with stable, low limits — ahead of everything currently in the August cascade.
