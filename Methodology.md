# Methodology

## 1. Data Profiling

Each source file was reviewed for row counts, column counts, date coverage, duplicate records, missing values, and metric consistency. This step identified the analytical grain and exposed limitations before any KPI calculations were made.

## 2. Data Quality Assessment

The quality review checked:

- Invalid or missing dates
- Duplicate rows
- Null values in metric fields
- Whether row-level `Total` values matched the sum of service columns
- Whether aggregate `Total` rows should be excluded from customer-level analysis

The project stores validation evidence in `data/pipeline_validation.json`.

## 3. Data Cleaning

The pipeline standardizes date fields, removes unusable records, normalizes service metrics, and prepares consistent silver-layer files for each source dataset.

## 4. Analytics Modeling

Cleaned wide source tables are transformed into an analytics-ready long fact table:

- `data/gold/fact_activity_by_entity_date.csv`
- `data/gold/dim_entity.csv`
- `data/gold/dim_activity.csv`
- `data/gold/dim_date.csv`

This structure supports time-series analysis, service mix reporting, customer concentration analysis, and regional comparisons.

## 5. KPI Development

KPIs were defined around operational workload and demand composition:

- Total applications
- Total searches
- Total transactions
- Search-to-application rate
- Transaction-to-application rate
- Average and median monthly application volume
- Application growth indicator
- Largest service category
- Top region by volume
- Top customer by volume

## 6. Exploratory Analysis

The analysis examined:

- Monthly demand trends
- Service mix
- Regional demand
- Customer volume distribution
- Top customer contribution
- Data quality patterns
- Funnel-style relationships between applications, searches, and transactions

## 7. Dashboard Design

Dashboard recommendations were created from the KPI framework and exploratory findings, focusing on demand monitoring, service mix, customer concentration, regional workload, and data quality.

