# Phase 6 — Terminal Value & Equity Bridge

## Objective
Calculate Terminal Value via both Perpetuity Growth and Exit Multiple methods, discount everything to present value, and bridge Enterprise Value to an implied share price.

## Explicit period (FY26E–FY30E)
| | Sum |
|---|---|
| PV of Explicit UFCF (5 years, discounted at 12.93% WACC) | ₹1,10,870 Cr |

## Terminal Value — Perpetuity Growth Method
| | Value |
|---|---|
| Terminal Growth Rate (g) | 4.0% |
| Terminal UFCF (FY31) | ₹37,664 Cr |
| Terminal Value (undiscounted) | ₹4,21,953 Cr |
| PV of Terminal Value | ₹2,29,769 Cr |
| **Enterprise Value** | **₹3,40,639 Cr** |

## Terminal Value — Exit Multiple Method
| | Value |
|---|---|
| Exit EV/EBITDA Multiple | 8.5x |
| EBITDA (FY30E) | ₹59,795 Cr |
| Terminal Value (undiscounted) | ₹5,08,255 Cr |
| PV of Terminal Value | ₹2,76,764 Cr |
| **Enterprise Value** | **₹3,87,634 Cr** |

## Equity Bridge (both methods use FY25 actuals)
| | Perpetuity Growth | Exit Multiple |
|---|---|---|
| Enterprise Value | 3,40,639 | 3,87,634 |
| (+) Cash & Equivalents | 24,455 | 24,455 |
| (−) Total Debt | 0 | 0 |
| (−) Minority Interest | 385 | 385 |
| **Equity Value** | **3,64,709** | **4,11,704** |
| ÷ Diluted Shares (Cr) | 415.2 | 415.2 |
| **Implied Share Price** | **₹878.38** | **₹991.57** |

## Reading the output
The two Terminal Value methods now converge to a tight ~1.13x range (₹878 vs ₹992/share) — a healthy level of agreement between a purely theoretical method (Perpetuity Growth) and a market-grounded one (Exit Multiple), and a strong signal that the underlying WACC and cash flow build are internally consistent.

Terminal Value represents 67.5% of total Enterprise Value under the Perpetuity Growth method (2,29,769 / 3,40,639) — comfortably inside the typical 60–80% range for a DCF.

**Worth noting for interview discussion:** the implied share price range (₹878–₹992) sits below Infosys's actual recent trading range. This isn't necessarily a flaw — a DCF represents an independent intrinsic view, not the market's price — but it's worth having a point of view on *why* the gap exists (e.g., whether the market is pricing in a lower risk premium, faster medium-term growth, or M&A optionality not captured in this base case) rather than treating the divergence as an error to explain away.

## Checkpoints (final state)
- [x] Both Terminal Value methods built side by side
- [x] g (4.0%) is comfortably below WACC (12.93%)
- [x] Discount factors decline smoothly (0.886 → 0.545 across 5 years)
- [x] Terminal Value methods converge to a tight, defensible range
- [x] Equity Bridge uses FY25 actuals, not a forecast year