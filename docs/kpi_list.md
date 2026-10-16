# KPI list for data extraction

Companies: **E.ON, EnBW, RWE, Uniper**, from their FY2025 annual reports.
Years: **2025 and 2024** (each report shows the prior year next to the current one).

Copy values **exactly as reported** (original number format, original unit). Cleaning happens later in the pipeline, not during extraction.

| # | KPI name (use exactly this text) | ESRS reference |
|---|---|---|
| 1 | Scope 1 GHG emissions | E1-6 |
| 2 | Scope 2 GHG emissions (location-based) | E1-6 |
| 3 | Scope 2 GHG emissions (market-based) | E1-6 |
| 4 | Scope 3 GHG emissions | E1-6 |
| 5 | Total energy consumption | E1-5 |
| 6 | Share of renewable energy consumption | E1-5 |
| 7 | Employees (headcount) | S1-6 |
| 8 | Female employees (headcount) | S1-6 |
| 9 | LTIF | S1-14 |
| 10 | Revenue | company KPI |

Female *share* is not extracted. It is calculated in the gold layer from KPIs 7 and 8.

## Rules

- One row per company, year and KPI. That's roughly 80 rows in total.
- If a KPI isn't reported, **skip the row**. Don't invent or estimate.
- Use `scope_or_note` for anything that affects comparability (e.g. "Scope 3 market-based", "LTIF employees only", "headcount as of 31.12.").
- Always fill `source_document` and `source_page`. This is your audit trail, and a strong interview talking point.
- Page numbers in `source_map.md` are **PDF page numbers** (what your PDF viewer shows), not the numbers printed on the page.
