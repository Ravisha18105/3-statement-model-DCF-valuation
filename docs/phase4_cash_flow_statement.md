# Phase 4 — Cash Flow Statement & Dynamic Balance Sheet Closure

## Objective
Build the indirect-method Cash Flow Statement, calculate Closing Cash from first principles, and link it back into the Balance Sheet so the model balances dynamically rather than by plug.

## Structure
```
CFO = Net Income + D&A − ΔReceivables + ΔPayables − ΔInventory
CFI = − Capex
CFF = − Dividends Paid (± borrowings, immaterial for Infosys)
Net Change in Cash = CFO + CFI + CFF
Closing Cash = Opening Cash + Net Change in Cash
```

Closing Cash links (green) directly into the Balance Sheet's Cash line for every forecast year, replacing the Phase 3 placeholder.

## Why this was the hardest phase to debug
This phase is where the Check tab stopped producing false positives and started actually testing the model — which meant every latent error from earlier phases surfaced here. Several distinct bugs were found and fixed during this phase (full detail in `debugging_log.md`):

1. A false-positive Check formula that was comparing blank cells, not real totals, for all 3 historical years
2. A frozen forecast subtotal — Total Non-Current Assets stopped recalculating from FY27E onward
3. A double-counted Total Equity, caused by a subtotal row included inside its own SUM range
4. A dividend reference off-by-one — Other Equity stopped subtracting dividends from FY27E onward due to a reference pointing at a blank spacer row
5. A ₹1,708 Cr historical PP&E transcription error, traced back to the FY25 Annual Report and corrected at the source

Each of these initially looked like a Phase 4 problem (since they only became visible once the Check tab was testing real numbers), but the actual defects lived in Phase 1 and Phase 3. This is the clearest illustration in the whole project of why an audit trail matters more than a single passing checkmark.

## Final state
| Check tab (Assets − (Liabilities+Equity)) | FY23 | FY24 | FY25 | FY26E | FY27E | FY28E | FY29E | FY30E |
|---|---|---|---|---|---|---|---|---|
| Result | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Balance Sheet balances genuinely across all 8 years — 3 historical, 5 forecast — with no plug, no hardcoded override, and no residual gap.

## Checkpoints (final state)
- [x] CFO, CFI, CFF calculate correctly for all 5 forecast years
- [x] Sign logic correct throughout (Capex negative, Dividends negative, ΔReceivables reduces CFO, ΔPayables increases CFO)
- [x] Opening Cash (FY26) = Closing Cash (FY25) from the historical Balance Sheet
- [x] BS Cash line links to CFS Closing Cash for every forecast year
- [x] Check tab shows genuine 0 across all 8 years