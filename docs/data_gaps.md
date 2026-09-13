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
- No volume targets or new-channel candidates have been supplied for Turkey's Sept–Oct plan.
- `docs/roadmap_sept_oct_2026.md` tracks this as pending; `docs/geo_progress_comparison.md` deliberately uses a per-$100k cost sensitivity instead of a volume projection so it doesn't depend on this gap being closed.

## 4. Conversion-rate (FTD/STD) coverage is thin

- Turkey: only **E4A** has conversion data on file (50–70%). BigIdea, Prime, Favori, Corytech, and Astrum have none.
- China: only **TCL** (both payin at 90%, and payout at 85/85%) has conversion data. Fastsecurepay and Moneystery have none.
- In `docs/payment_cascades.md`, missing conversion data is treated as "unmeasured, monitor once live" — it is **not** treated as a failure, and a channel is never penalized in the proposed cascade for lacking this data. Only E4A is flagged, because it has data and that data is below the review floor.

## 5. New China channel (HTX P2P +3%) — cost not verified against live quotes

- The rate structure (HTX P2P + 3%, USDT→CNY) is confirmed for Sept–Oct, but the actual cost relative to TCL's current 2.7% effective payout margin depends on live HTX P2P pricing vs. TCL's xe.com reference at settlement time.
- Not yet checked. See `docs/roadmap_sept_oct_2026.md` and `docs/cost_analysis.md`.

## 6. Broader rate-card candidates excluded by design, not by oversight

- The multi-GEO rate card lists roughly 30 Turkey and 16 China channel/method combinations beyond the ones in this pack — many paused, in negotiation, unresponsive, or archived, and never carrying tracked volume.
- Per scope agreed for this pack, only channels the volume tracker marks as active are included. The excluded candidates are not "missing data" — they're out of scope by design. If a future review needs the full candidate universe (e.g. to source a Forex or Adult backup channel), that's a separate exercise against the full rate card, not a gap in this one.
