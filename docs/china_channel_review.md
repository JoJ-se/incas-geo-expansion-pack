# China — Channel Review

**Period:** August (actuals)
**Sources:** Monthly channel/volume tracker (status, cascade line, volume) + multi-GEO rate card (commission/settlement terms), merged by channel name. Only channels tracked as active in the volume tracker are included — see `README.md` for scope rationale.

---

## Channels

| Channel | Method | Vertical | Status | Cascade line | AFU | Daily vol (USDT) | Monthly vol (USDT) | PayIn | PayOut | FX source | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|
| TCL | Alipay simple payin | Low/mid risk + betting + forex | Live | L1 | Yes | 0 | 0 | 4.5% (+0.2% agent) | — | Okex +0.12 CNY | Conv. 90% — cheapest and best-tested payin channel, traffic not launched |
| TCL | Alipay simple payout | Low/mid risk + betting + forex | Live | L1 | Yes | 52,000 | 1,500,000 | — | 2.7% (+0.2% agent) | xe.com | Carries essentially all of China's tracked volume; conv. 85/85%; "very stable" |
| TCL | Alipay payout corporate | Low risk only | In integration | L1 | Yes | N/A | N/A | — | — | — | In integration; no rate published yet |
| TCL | WeChat payin, UnionPay QR payin | Low risk only | In integration | L1 | Yes | N/A | N/A | — | — | — | In integration; no rate published yet |
| TCL | Alipay payin (Adult) | Adult | In integration | — | — | N/A | N/A | — | — | — | In integration; no rate published yet |
| Fastsecurepay | Alipay simple payin | Low risk only | Live | L1 | Yes | 0 | 0 | **Not confirmed** | — | — | Rate card has a 1.5% Alipay rate for this partner, but tagged as PayOut — direction mismatch with this PayIn line. See `docs/data_gaps.md`. |
| Moneystery | Alipay native payin | Adult only | Live | L1 | Yes | 0 | 0 | 9.5% | — | Okex +0.3 CNY | Most expensive live channel in China; Adult-vertical exclusive; traffic not launched |

Raw extract: [`data/china_channels_august.csv`](../data/china_channels_august.csv), [`data/china_rate_card.csv`](../data/china_rate_card.csv)

---

## August review notes (as recorded by the payments team)

> In August we updated offers, flows and limits across all channels. Completed the Fastsecurepay integration with better Alipay payout rates. Fixed a unified Alipay-payout balance top-up rate across all merchants to capture margin from the FX spread. Agreed new verticals with TCL on simple Alipay payin/payout — betting + forex. Sent new verticals into integration with TCL: WeChat payout, corporate Alipay, Adult.

## New idea on file (China only)

> A card top-up product for Chinese tourists: top up RUB cards (virtual or plastic, issued in Russia) via Alipay. Two routes considered — (1) partner with a card-issuing acquirer who holds RUB liquidity and owns the top-up interface, with Incas handling the Alipay-wallet debit (payin) and settlement/reconciliation; or (2) Incas builds its own top-up storefront and integrates directly with a non-resident card issuer, without an intermediary partner.

This is a genuinely new line of business, not a channel-cost item — kept here for visibility, not folded into the cost tables.

## What this actually shows

- **All three payin-side channels (TCL, Fastsecurepay, Moneystery) are at zero volume as of August.** China's entire tracked volume is on TCL's payout leg. There is no "cheap idle vs. expensive active" comparison to make on the payin side yet — all three are pre-launch.
- **Among the payin candidates, TCL is clearly the strongest once traffic starts**: cheapest (4.5%) and only one with conversion data (90%). Moneystery (9.5%) is the expensive option, but it's also the only Adult-vertical channel, so it isn't a like-for-like substitute — it's the necessary cost of running that vertical, not routing inefficiency.
- **Fastsecurepay's rate is unresolved.** The one figure on file is tagged as a payout rate in the rate card, while the tracker uses this partner for payin. Treat this as an open item, not a usable payin cost, until confirmed with the payments team.
- **TCL's payout side is already the cost anchor** for real volume (2.7%, 85% conversion, "very stable") — there is no cheaper *confirmed* live payout alternative to reallocate into today. See `docs/roadmap_sept_oct_2026.md` for the one confirmed change coming: a new payout channel via HTX P2P +3%.

---

## September–October 2026 (plan)

**Payout — two new channels planned:**

1. **Confirmed:** a new Alipay payout channel priced at **HTX P2P + 3%** (nominal). Compared against TCL's all-in cost (2.7% payout + 0.2% agent + xe.com reference = **2.9% all-in**), the nominal margins look close — the HTX +3% is a single fee blended directly against the live exchange rate, not a separate markup stacked on a reference rate the way TCL's structure is. Per the payments team, once the live HTX P2P rate is accounted for, the true all-in cost comes out **roughly 4 percentage points lower**. This figure is provided directly by the payments team, not derived from either source spreadsheet — see `docs/data_gaps.md`.
2. **Candidate, rate not yet confirmed:** a second new payout channel fills the tracker's remaining "New channel" slot for September. Kept as a pipeline item, not cost-ranked, until a rate is confirmed.

Proposed cascade: the confirmed HTX channel and TCL both at L1, TCL kept for its proven stability while the new channel absorbs the cost-sensitive share of volume; the second new channel joins once its rate is confirmed.

**Payin:** no rate changes confirmed, but a volume ramp is targeted — see the growth targets below.

**Growth targets (by end of October), as provided:**

| Metric | August | End of October (target) |
|---|---|---|
| Payout volume | 1,500,000 USDT/mo | 3,000,000 USDT/mo |
| Payin volume | 0 | ~50,000 USDT/day (≈1,500,000 USDT/mo) |
| Blended margin | 0.1% | 4–5% |

These are targets as given, not figures this pack derives — flagged here rather than presented as already-achieved.

**Additional confirmed targets for the period:**

- Activate corporate payout / WeChat & UnionPay payout, once the corresponding integration clears.
- Grow volume into additional verticals — Adult, High Risk.
- Finish integration and launch WeChat Payin.

The tracker's own September tab rolls the same channels forward (plus TCL WeChat payout) with all data columns blank, plus 2 open "New channel" slots — both now filled by the two payout channels above.
