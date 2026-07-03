# HM Land Registry Operations and Demand Analytics



## Project Overview

This project analyzes application, transaction, search, customer, local authority, and regional data to answer practical operational questions:

- Which service categories drive the highest workload?
- How concentrated is activity across customers?
- Which regions generate the most demand?
- What data quality issues affect reporting confidence?
- Which KPIs should be monitored in an operational dashboard?


## Key Findings

- Latest application volume: 1,541,143
- Latest transaction volume: 66,426
- Latest search volume: 210,935
- Mean data quality score: 97.16
- Largest service category: OC1
- Highest-volume region: South East
- Highest-volume customer: Enact


## Repository Structure

```text
.
|-- README.md
|-- PROJECT_SUMMARY.md
|-- METHODOLOGY.md
|-- DATA_DICTIONARY.md
|-- pipelines/
|-- reports/
|-- data/
|   |-- silver/
|   `-- gold/
|-- assets/
|-- analysis_charts/
|-- analysis_outputs/
`-- outputs/
```

## Live Report

View the interactive HTML report here:

[Open the Live Report](https://foroozane.github.io/Land-Registry-Business-and-Operational-Analytics/)

## How to Run

Install dependencies:

```powershell
python -m pip install -r requirements.txt
```

Build analytics-ready tables:

```powershell
python pipelines/build_analytics_ready.py
```

Regenerate engineering documentation:

```powershell
python reports/generate_deliverables.py
```

Regenerate the analytical report:

```powershell
python build_analysis_report.py
```

Validate the analytical report:

```powershell
python verify_land_registry_report.py
```