# Source map: where each KPI is in the reports

PDF page numbers (as shown in your PDF viewer). Always check the value and unit on the page itself. This map only tells you where to look.

| KPI | E.ON | EnBW | RWE | Uniper |
|---|---|---|---|---|
| Scope 1, 2, 3 GHG emissions | p100 | p169 | p114 | p149–150 |
| Total energy consumption, renewable share | p101 | p165 | p113 | p147 |
| Employees, female employees (headcount) | p123 (also p66) | p207 | p147–148 | p187 |
| LTIF | p120 | p208 | p149 | ~p192–193 |
| Revenue | p151 (income statement, "Sales") | p108 | p166 | p2 / income statement ("Sales") |

## Quirks spotted while mapping

These are exactly the issues your silver layer has to solve. Note each one in `scope_or_note` as you extract.

- **Emission units differ:** E.ON and RWE report in *million* t CO2e, EnBW in *thousand* t CO2e, Uniper in t CO2e.
- **Energy units differ:** RWE, EnBW and Uniper report MWh (EnBW also GWh on p402). Check E.ON's unit on p101.
- **Scope 3 variants:** E.ON reports Scope 3 both location- and market-based. Pick one rule (e.g. market-based) and apply it everywhere.
- **Uniper's prior-year emissions were restated** (see the footnotes on p149–150). Use the 2024 figure as shown in the FY2025 report and note "restated".
- **LTIF definitions differ:** E.ON splits employees / contractors / combined; EnBW changed its definition in 2025 ("LTIF overall" vs. "old"). Note which variant you take.
- **Employee totals differ by scope:** some tables include temporary staff or the whole group, others don't (e.g. RWE shows two different totals on p147 and p148). Note which one you take.
- **Revenue naming:** "Sales" (E.ON, Uniper) vs. "Revenue" (EnBW, RWE). EnBW also shows a much smaller revenue figure on p86, so make sure you take the consolidated group figure.
- **Number formats:** "1,234.5" (English reports) vs. "1.234,5". Keep them as reported. Parsing is the pipeline's job.
