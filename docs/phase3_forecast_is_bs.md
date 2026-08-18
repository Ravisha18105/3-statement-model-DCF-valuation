# Phase 3 — Forecasting the Income Statement & Balance Sheet

## Objective
Forecast the IS and BS for FY26E–FY30E, driven by the Assumptions tab, with PP&E and Working Capital built as standalone rollforward schedules rather than inline formulas.

## Income Statement forecast (FY26E–FY30E, ₹ Cr)
| Metric | FY26E | FY27E | FY28E | FY29E | FY30E |
|---|---|---|---|---|---|
| Revenue | 1,74,399 | 1,86,607 | 1,99,297 | 2,12,251 | 2,26,047 |
| Total Expenses | 1,38,011 | 1,47,671 | 1,57,713 | 1,67,965 | 1,78,882 |
| Profit Before Tax | 44,550 | 47,855 | 51,308 | 54,643 | 58,195 |
| Profit for the year | 32,076 | 34,456 | 36,942 | 39,343 | 41,901 |

*(Revenue derived from FY25 base of ₹1,62,990 Cr compounded at the Phase 2 growth assumptions.)*

## PP&E Schedule (rollforward)
| | FY25 (anchor) | FY26E | FY27E | FY28E | FY29E | FY30E |
|---|---|---|---|---|---|---|
| Closing Gross PP&E | 31,290 | 33,732 | 36,344 | 39,234 | 42,354 | 45,745 |
| Closing Accum. Depreciation | 19,512 | 22,172 | 25,039 | 28,128 | 31,463 | 35,063 |
| **Net PP&E** | **11,778** | 11,560 | 11,305 | 11,106 | 10,891 | 10,682 |

The FY25 anchor point (11,778) matches the corrected filing figure — see Phase 1 note. Net PP&E gently declines over the forecast because the depreciation rate (8.5% of gross) outpaces capex additions (~1.4%–1.5% of revenue) — a realistic pattern for an asset-light business not aggressively expanding its fixed asset base.

## Working Capital Schedule
| | FY25 | FY26E | FY27E | FY28E | FY29E | FY30E |
|---|---|---|---|---|---|---|
| Receivables | 31,158 | 33,446 | 35,276 | 37,675 | 39,543 | 42,113 |
| Payables | 4,164 | 4,537 | 4,855 | 4,753 | 5,062 | 5,391 |
| Inventory | 0 | 0 | 0 | 0 | 0 | 0 |

## Balance Sheet — key forecast logic
- **Equity Share Capital:** held flat (no new issuance modeled)
- **Other Equity:** rolled forward as `Prior + Net Income − Dividends`, where Dividends = Net Income × 65% payout ratio
- **Immaterial/no-clean-driver lines** (Investments, DTA/DTL, lease liabilities, other financial assets/liabilities): held flat — explicit simplification, not an oversight
- **Provisions:** driven by 1% of Revenue (linked to Employee Benefit Expense economics)
- **Cash:** left as a placeholder through Phase 3, resolved in Phase 4

## Checkpoints (final state)
- [x] Revenue/EBIT/Net Income flow from Assumptions tab drivers
- [x] PP&E schedule anchors correctly to the corrected FY25 Net PP&E (11,778)
- [x] Working Capital schedule outputs link (green) into the BS
- [x] All BS subtotals (Total Non-Current Assets, Total Current Assets, Total Equity, etc.) are genuine `SUM()` formulas across every forecast year