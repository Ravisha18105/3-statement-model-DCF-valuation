# Phase 1 — Excel Setup & Historical Financials

## Objective
Establish the workbook structure, color-coding convention, and transcribe 3 years (FY23–FY25) of Infosys's consolidated Income Statement, Balance Sheet, and Cash Flow Statement from public filings.

## What was built
- 12-tab workbook: `Cover`, `Assumptions`, `IS`, `BS`, `CFS`, `PP&E Sch`, `WC Sch`, `WACC`, `UFCF`, `DCF`, `Sensitivity`, `Check`
- Color convention: 🔵 blue = hardcode, ⚫ black = same-sheet formula, 🟢 green = cross-tab link
- Historical figures transcribed from Infosys's Integrated Annual Reports (Consolidated, Ind-AS, ₹ Crores)

## Key historical figures (as transcribed)
| Metric (₹ Cr) | FY23 | FY24 | FY25 |
|---|---|---|---|
| Revenue from operations | 1,24,014 | 1,53,670 | 1,62,990 |
| EBIT | 31,800 | 36,458 | 38,024 |
| Net Income | 23,268 | 26,248 | 26,750 |
| Net PP&E | 13,346 | 12,370 | 11,778 |
| Total Assets | 1,01,337 | 1,37,814 | 1,48,903 |
| Total Equity | 67,745 | 88,461 | 96,203 |

## Issue found and corrected post-Phase-1
A transcription error was initially found in the PP&E schedule's historical Gross PP&E / Accumulated Depreciation figures for FY24 and FY25 — the model's originally computed Net PP&E didn't match the actual filing. This was traced directly against the FY25 Annual Report's Consolidated Balance Sheet (page 302) and corrected at the source; the figures above reflect the corrected values. See `debugging_log.md` for the full trace.

**Lesson carried forward:** historical subtotals (e.g., Total Non-Current Assets) were originally entered as hardcoded totals matching the filing, separate from the sum of their own line items. This masked the PP&E error for an entire phase. All historical subtotals were subsequently converted to genuine `SUM()` formulas so any future transcription gap surfaces immediately via the Check tab, rather than being hidden by a hardcoded total.

## Checkpoints (final state)
- [x] All 3 historical years transcribed in blue, matching filings line-by-line
- [x] Historical subtotals are `SUM()` formulas, not hardcodes
- [x] Check tab confirms Total Assets = Total Liabilities + Equity for FY23–FY25