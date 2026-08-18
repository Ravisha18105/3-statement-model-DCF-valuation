# Sources

Historical financial data used in this model was transcribed from Infosys Ltd's publicly filed **Consolidated** financial statements (Ind-AS, ₹ Crores), sourced from the Integrated Annual Reports available on Infosys's investor relations page:

- Infosys Integrated Annual Report FY2025 — Consolidated Balance Sheet, Statement of Profit and Loss, Statement of Cash Flows
- Infosys Integrated Annual Report FY2024 — used for FY23/FY24 comparative figures

🔗 Infosys Investor Relations: https://www.infosys.com/investors.html
(Locate "Integrated Annual Report" under Financial Results / Annual Reports; consolidated financials are typically ~page 300+ of the PDF.)

## WACC inputs

| Input | Value | Source |
|---|---|---|
| Risk-free rate | 6.77% | 10-Year Government of India bond yield |
| Beta | 0.86 | NSE:INFY (domestic-listed), not the US-listed ADR — see `docs/debugging_log.md` #6 for why this distinction matters |
| Equity Risk Premium | 7.27% | India-specific ERP |
| Exit multiple | 8.5x | EV/EBITDA, benchmarked against comparable Indian IT services peers (TCS, Wipro, HCL Tech) |

> Note: Filing PDFs are not committed to this repository (see `.gitignore`) as they are third-party copyrighted documents — this file links directly to the source instead.