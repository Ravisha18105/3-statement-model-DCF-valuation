# Debugging Log

A record of real integration bugs found while building this model, why they happened, and how they were traced. Kept intentionally as evidence of audit process, not just final output.

---

### 1. False-positive Check tab formula
**Symptom:** Check tab showed 0 (balanced) for all historical years.
**Root cause:** The Balance Sheet had been restructured (rows inserted for new line items) after the Check tab formula was first written. The formula was still referencing old row numbers that pointed at blank cells — so it was computing `blank − (blank + blank) = 0`, not actually testing Assets against Liabilities + Equity.
**Fix:** Rewrote the Check formula to reference the current `Total Assets` and `Total Equity + Liabilities` rows directly.
**Lesson:** A checkpoint that always shows green needs to be interrogated the first time it matters — a passing check on cells that were never wired to real data is worse than no check at all, because it creates false confidence.

### 2. Frozen forecast subtotal
**Symptom:** "Total Non-Current Assets" showed the exact same figure across FY27E–FY30E despite individual line items (PP&E, CWIP) changing year to year.
**Root cause:** When the SUM formula was dragged right, one row picked up `=F20` (copy the cell to the left) instead of `=SUM(G8:G19)` (re-sum that column's own components).
**Fix:** Re-entered the SUM formula explicitly in each forecast column.
**Lesson:** Always spot-check that a dragged formula's *relative references* updated as intended — a silently frozen subtotal produces numbers that look plausible but are structurally wrong.

### 3. Double-counted Total Equity
**Symptom:** FY25 historical Total Equity computed to ~₹192,021 Cr instead of the filed ₹96,203 Cr — almost exactly double.
**Root cause:** `Total Equity = SUM(row37:row40)` included row 39 ("Total equity attributable to equity holders"), which was itself a subtotal of rows 37 and 38 — so Share Capital and Other Equity were being counted twice.
**Fix:** Changed the formula to `= row39 + row40` (subtotal + NCI), rather than re-summing the components that were already inside the subtotal.
**Lesson:** Never include a subtotal row inside a SUM range that also contains that subtotal's own components.

### 4. Dividend reference off-by-one
**Symptom:** Other Equity grew far faster than expected from FY27E onward.
**Root cause:** The Other Equity rollforward formula correctly referenced the Dividend Payout Ratio assumption in FY26E, but when dragged right, the reference shifted to a blank spacer row instead of the payout ratio row in every subsequent year — so 100% of Net Income was being retained with no dividend deduction.
**Fix:** Corrected the cell reference and re-dragged.
**Lesson:** A blank row directly above or below an assumption is a common source of silent off-by-one errors when formulas are dragged across many columns — worth double-checking any reference that sits adjacent to a spacer row.

### 5. Historical PP&E transcription error (₹1,708 Cr)
**Symptom:** Balance Sheet balanced for all historical years but showed a flat, non-growing imbalance of exactly −1,708 across every forecast year.
**Root cause:** The flat (non-compounding) nature of the gap indicated a one-time historical anchoring error rather than a forecast formula bug. Tracing it: historical "Total Non-Current Assets" had been hardcoded directly from the filing's stated total (₹51,804 Cr), but the individual line items beneath it only summed to ₹50,096 Cr — a ₹1,708 Cr gap sitting undetected inside the historical data itself. Cross-referencing the FY25 Annual Report's Consolidated Balance Sheet (page 302) confirmed Net PP&E was transcribed as ₹10,070 Cr when the filing actually stated ₹11,778 Cr (a related error was also found in the FY24 column).
**Fix:** Corrected the underlying Gross PP&E / Accumulated Depreciation hardcodes in the PP&E schedule against the filing, and converted the historical subtotal from a hardcode to a genuine `SUM()` formula so future transcription errors would surface immediately instead of being masked by a hardcoded total.
**Lesson:** Hardcoding a subtotal directly from a source document, separately from summing its own components, creates a blind spot — if the two don't reconcile, nothing will flag it until something downstream depends on the row-level detail.

### 6. Understated beta in the WACC build
**Symptom:** WACC computed to 7.66%, implying Cost of Equity of only 7.71% — implausibly low for an equity investment, and pulling the DCF's terminal value (and implied share price) sharply upward.
**Root cause:** The beta input had been sourced from a US-listed ADR ticker measured against the S&P 500, rather than the domestically-listed NSE ticker measured against the relevant local index — understating Infosys's actual sensitivity to its primary market.
**Fix:** Replaced the beta with a figure sourced against the NSE-listed ticker (0.86), which produced a WACC of 12.93% — a materially more realistic discount rate for an Indian large-cap.
**Lesson:** A CAPM input sourced from the "wrong" listing of a dual-listed stock can look plausible in isolation (it's still a real, published number) while being the wrong number for the valuation's currency and market context. Always check which index and listing a beta was measured against, not just where it came from.

---

**General takeaway:** every one of these bugs passed silently for at least one phase before surfacing. The Check tab is only as good as the formulas feeding it — building the habit of tracing *why* a number is wrong, not just patching until a checkmark turns green, was the actual skill being practiced here.