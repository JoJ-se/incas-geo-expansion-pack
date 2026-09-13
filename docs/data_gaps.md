# Data Gaps

Every unresolved discrepancy or missing figure found while building this pack, in one place. Nothing in the other documents assumes an answer to any of these — check here before treating a number as final.

---

## 1. Fastsecurepay — payin vs. payout direction mismatch (China)

- The channel/volume tracker lists **Fastsecurepay** under **Alipay simple payin** (Low risk only, Live, currently 0 volume, "in the process of launching traffic").
- The rate card's only Fastsecurepay entry is for **Alipay payout** (1.5%, via "OKX P2P –0.02").
- These don't describe the same flow. The 1.5% figure is **not** used anywhere in this pack as Fastsecurepay's payin cost.
- **Needs:** confirmation from the payments team of Fastsecurepay's actual payin rate, or confirmation that the tracker's method label should be payout instead.

## 2. TCL — three lines with no published rate yet (China)

- Corporate Alipay payout, WeChat/UnionPay QR payin, and Alipay payin (Adult) are all listed as **"In integration"** in the tracker, with no corresponding row in the rate card.
- Not a discrepancy — just not far enough along yet. Kept out of the cost tables and cascades until a rate is published and status moves to Live.

## 3. Turkey Sept–Oct 2026 targets — not provided

- The tracker's September tab exists but is blank (channel names only, no volume/status/AFU data).
- New-channel candidates (Continental, BnPay) and Astrum's renegotiated rate are now confirmed — see `docs/roadmap_sept_oct_2026.md`. **Volume targets are still not provided.**
- `docs/geo_progress_comparison.md` deliberately uses a per-$100k cost sensitivity instead of a volume projection so it doesn't depend on this gap being closed.

## 3a. Continental and BnPay — confirmed for cascade, not yet in the standard rate card

- Both channels are confirmed at 4.5% PayIn for Sept–Oct cascade placement, provided directly by the payments team.
- Continental doesn't appear in either of this pack's two source spreadsheets at all. BnPay appears in the broader multi-GEO rate card as a paused candidate (4.5%/7.5%, "Start 10/09") that was previously out of scope per this pack's active-channels-only rule — it's now in scope because it's a confirmed Sept–Oct addition.
- **Needs:** both channels added to the standard rate card / channel tracker with full terms (limits, settlement, FX source) once integration is further along.

## 4. Conversion-rate (FTD/STD) coverage is thin

- Turkey: only **E4A** has conversion data on file (50–70%). BigIdea, Prime, Favori, Corytech, and Astrum have none.
- China: only **TCL** (both payin at 90%, and payout at 85/85%) has conversion data. Fastsecurepay and Moneystery have none.
- In `docs/payment_cascades.md`, missing conversion data is treated as "unmeasured, monitor once live" — it is **not** treated as a failure, and a channel is never penalized in the proposed cascade for lacking this data. Only E4A is flagged, because it has data and that data is below the review floor.

## 5. New China channel (HTX P2P +3%) — cost confirmed, but by input rather than by source spreadsheet

- **Resolved as of this update:** the payments team has confirmed the new channel's all-in cost is roughly **4 percentage points lower** than TCL's (2.9% all-in), because HTX's live P2P USDT→CNY rate runs more favourably than TCL's xe.com reference.
- Flagged here for provenance, not as an open question: this 4pp figure, and the related growth targets (payout volume 1.5M→3M, payin 0→50k/day, margin 0.1%→4–5%), are **provided directly by the payments team in this session**, not derived from either of the two original source spreadsheets. Treat them with the same confidence as a direct team statement, not as independently verified against a live quote by this pack.
- See `docs/roadmap_sept_oct_2026.md` and `docs/cost_analysis.md`.

## 5a. Prime's limits/traffic-fit rationale — provided context, not in either spreadsheet

- Neither source spreadsheet states that Prime's settlement limits are lower/more stable than other Turkey channels, or that Incas' Turkey traffic is small-ticket by design. This context was provided directly by the payments team and is now reflected in `docs/cost_analysis.md`, `docs/turkey_channel_review.md`, and `docs/payment_cascades.md`.
- It changes the *interpretation* of the cost gap (a deliberate limits/stability trade-off, not neglect of a cheaper channel) but not the underlying numbers, which remain sourced from the two spreadsheets.

## 6. Broader rate-card candidates excluded by design, not by oversight

- The multi-GEO rate card lists roughly 30 Turkey and 16 China channel/method combinations beyond the ones in this pack — many paused, in negotiation, unresponsive, or archived, and never carrying tracked volume.
- Per scope agreed for this pack, only channels the volume tracker marks as active are included. The excluded candidates are not "missing data" — they're out of scope by design. If a future review needs the full candidate universe (e.g. to source a Forex or Adult backup channel), that's a separate exercise against the full rate card, not a gap in this one.
