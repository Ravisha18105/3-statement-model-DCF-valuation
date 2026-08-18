# Phase 2 — Operating Drivers

## Objective
Compute historical operating ratios from the 3-statement historicals and set forward-looking assumptions to drive the 5-year forecast (FY26E–FY30E).

## Drivers built (Assumptions tab)

| Driver | FY23 (hist) | FY24 (hist) | FY25 (hist) | FY26E–FY30E assumption |
|---|---|---|---|---|
| Revenue Growth % | — | 23.9% | 6.1% | 7.0% → 6.5% (tapering) |
| EBIT Margin | 25.6% | 23.7% | 23.3% | held ~23.3%–23.5% |
| Net Margin | 18.8% | 17.1% | 16.4% | held ~16.5%–16.7% |
| DSO (days) | 61.1 | 71.7 | 69.8 | 68–70 |
| DPO (days) | 9.2 | 11.8 | 11.8 | 11–12 |
| DIO (days) | 0 | 0 | 0 | 0 (services business, no inventory) |
| Capex % of Revenue | 1.7% | 1.4% | 1.4% | 1.4%–1.5% |
| Effective Tax Rate | 26.5% | 27.1% | 28.9% | held at 28.0% |
| Depreciation % of Gross PP&E | — | — | — | held at 8.5% |
| Dividend Payout Ratio | — | — | — | held at 65.0% |
| CWIP % of Capex | — | — | — | held at 30.0% |
| Provisions % of Revenue | — | — | — | held at 1.0% |

## Notes on judgment calls
- **Revenue growth tapering from 7.0% to 6.5%** reflects a conservative normalization versus FY24's unusually high 23.9% (a post-pandemic demand catch-up year, not representative of steady state) and FY25's more muted 6.1%.
- **DIO held at 0** — correctly reflects Infosys as an asset-light services business with no meaningful inventory, confirmed by historical data showing 0 across all 3 years.
- **Dividend payout ratio (65%)** was calculated from Infosys's historical payout pattern and is the key driver of the Other Equity rollforward in Phase 3/4.
- **Capex % of revenue (1.4%–1.5%)** stays in a narrow, low band — consistent with an asset-light services business and part of why Infosys was chosen for this build.

## Checkpoints (final state)
- [x] All historical ratios computed via green (cross-tab) formulas, not hardcoded
- [x] Historical DSO/DPO/DIO trend is sensible (no wild swings unexplained by the business)
- [x] Forecast assumptions typed in blue for all 5 forecast years, for every driver