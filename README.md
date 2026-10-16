# ESG Data Pipeline & Reporting Dashboard

> Status: **in progress** (started October 2026)

End-to-end data pipeline that ingests sustainability KPIs published by four German energy utilities, cleans and validates them, and models them in a medallion architecture (bronze / silver / gold) on Databricks. A Power BI dashboard on top of the gold layer compares emissions, energy consumption, workforce and company KPIs.

The project builds on my bachelor thesis, a comparative analysis of sustainability reporting by German utilities under CSRD/ESRS, which showed how inconsistent published ESG data is across companies (units, scopes, number formats, boundaries).

## Architecture

```
Sustainability reports (PDF)
        │  manual extraction with source page references
        ▼
data/raw/*.csv
        │  Python ingestion
        ▼
BRONZE   raw data as reported, plus load metadata
        │  SQL: type casting, unit normalization, deduplication, validation
        ▼
SILVER   clean, comparable KPI values in standard units
        │  SQL: aggregation and KPI calculation
        ▼
GOLD     analysis-ready tables (e.g. emissions intensity per employee / per revenue)
        │
        ▼
Power BI dashboard
```

## Tech stack

Python · SQL · Databricks (Free Edition, Unity Catalog, Delta tables) · Power BI · Git

## Repository structure

```
data/raw/        raw extracted KPIs (CSV)
scripts/         Python ingestion
sql/silver/      cleaning and validation logic
sql/gold/        KPI models for reporting
notebooks/       Databricks notebooks
dashboard/       Power BI file and screenshots
docs/            KPI definitions and design decisions
```

## Data quality checks

_To be documented: checks applied in the silver layer and what they caught._

## Key findings

_To be added once the dashboard is complete._
