# Phase 7 — Sensitivity Analysis

## Objective
Build 2D Data Tables showing how the implied share price moves across a realistic range of WACC and terminal value assumptions, for both Terminal Value methods.

## Table structure
- **Table 1:** WACC (rows) × Terminal Growth Rate (columns) — feeds off the Perpetuity Growth implied share price
- **Table 2:** WACC (rows) × Exit EV/EBITDA Multiple (columns) — feeds off the Exit Multiple implied share price

Both built via Excel's native `Data → What-If Analysis → Data Table`, with the corner cell linked live to the DCF tab's implied share price output, row input cell pointed at the growth rate / multiple assumption, and column input cell pointed at the WACC assumption.

## How to read this
With WACC now at a realistic 12.93% and both Terminal Value methods converging cleanly, the sensitivity grid's base case sits credibly near the center of the tested range rather than at an extreme edge — a sign the underlying assumptions feeding the table are sound, not just internally consistent.

As with Phase 6, the useful output here isn't a single cell — it's the range. Reading the grid corner to corner (most conservative WACC/growth combination vs. most aggressive) gives a defensible bracket to speak to in an interview, rather than presenting one implied share price as a point estimate with false precision.

## Checkpoints (final state)
- [x] Both sensitivity tables built and populated with real, varying numbers
- [x] Base case falls within the grid's tested range, near its center
- [x] Color scale conditional formatting applied
- [x] Grid shows a smooth, monotonic gradient with no erratic jumps