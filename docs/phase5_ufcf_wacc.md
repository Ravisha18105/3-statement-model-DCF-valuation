# Phase 5 — Unlevered Free Cash Flow & WACC

## Objective
Convert the operating forecast into Unlevered Free Cash Flow (UFCF) and derive a defensible discount rate (WACC) via CAPM.

## UFCF Build (₹ Crores)
| | FY26E | FY27E | FY28E | FY29E | FY30E |
|---|---|---|---|---|---|
| EBIT | 40,635 | 43,666 | 46,835 | 49,879 | 53,121 |
| NOPAT (EBIT × (1−28% tax)) | 29,257 | 31,440 | 33,721 | 35,913 | 38,247 |
| + D&A | 2,660 | 2,867 | 3,089 | 3,335 | 3,600 |
| − Capex | 2,442 | 2,613 | 2,890 | 3,120 | 3,391 |
| − Δ Net Working Capital | 1,915 | 1,512 | 2,501 | 1,558 | 2,241 |
| **UFCF** | **27,560** | **30,182** | **31,420** | **34,569** | **36,215** |

## WACC Build
| Component | Value |
|---|---|
| Risk-Free Rate | 6.77% (10-yr GoI bond yield) |
| Beta | 0.86 (NSE:INFY, domestic-listed) |
| Equity Risk Premium | 7.27% |
| **Cost of Equity (CAPM)** | **13.05%** |
| Total Debt | ₹8,227 Cr |
| Interest Expense | ₹416 Cr |
| Cost of Debt (pre-tax) | 5.06% |
| Cost of Debt (after-tax, 28% rate) | 3.64% |
| Market Cap | ₹6,20,000 Cr |
| Weight of Equity | 98.7% |
| Weight of Debt | 1.3% |
| **WACC** | **12.93%** |

A beta of 0.86 (sourced against the domestic NSE listing rather than a US-listed ADR) sits in a realistic range for an IT services company with meaningful sensitivity to global tech spending cycles, and produces a WACC that's more in line with what's typical for an Indian large-cap.

## Checkpoints (final state)
- [x] NOPAT built from EBIT × (1 − tax rate), not from Net Income
- [x] UFCF = NOPAT + D&A − Capex − ΔNWC for all 5 forecast years
- [x] Cost of Equity via CAPM with current risk-free rate, domestic beta, and ERP
- [x] Weight of Equity uses market cap, not book value
- [x] WACC (12.93%) sits in a plausible range for an Indian large-cap