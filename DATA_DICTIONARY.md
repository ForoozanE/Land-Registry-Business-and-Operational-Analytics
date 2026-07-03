# Data Dictionary

## Source Datasets

| Dataset | Grain | Description |
| --- | --- | --- |
| `applications_all_customers.csv` | Customer by monthly reporting date | Application volumes by customer and service category |
| `transactions.csv` | Customer by monthly reporting date | Transaction volumes by customer and transaction type |
| `searches.csv` | Customer by monthly reporting date | Search volumes by customer and search type |
| `local_authority.csv` | Local authority by monthly reporting date | Application volumes by local authority and service category |
| `region.csv` | Region by monthly reporting date | Application volumes by region and service category |

## Common Fields

| Field | Description |
| --- | --- |
| `date` | Monthly reporting date |
| `Total` | Total volume for the row |
| `FR` | Freehold registration activity volume |
| `DFL` | Dispositionary first lease activity volume |
| `TP` | Transfer of part activity volume |
| `DLG` | Dealing activity volume |
| `OS(W)` | Official search of whole with priority |
| `OS(NPW)` | Official search of whole without priority |
| `OS(P)` | Official search of part with priority |
| `OS(NPP)` | Official search of part without priority |
| `SIMS` | Search of index map service volume |
| `OC1` | Official copy service volume |
| `OC2` | Official copy service volume |

## Entity Fields

| Field | Dataset | Description |
| --- | --- | --- |
| `Account Customer` | Customer-level files | Customer or account name |
| `Local Authority` | `local_authority.csv` | Local authority name |
| `Region` | `region.csv` | Geographic region |

## Gold Model

| Table | Description |
| --- | --- |
| `fact_activity_by_entity_date.csv` | Long-format activity fact table by entity, activity, and date |
| `dim_entity.csv` | Entity dimension containing customers, local authorities, and regions |
| `dim_activity.csv` | Activity or service category dimension |
| `dim_date.csv` | Date dimension for monthly reporting |

## Data Caveats

- Some rows are aggregate `Total` records and must be excluded from customer, local authority, or regional entity analysis.
- Source files have different end dates, so not every dataset supports the same time window.
- Customer names may appear in duplicate rows within the same reporting month and need aggregation before concentration analysis.
- The source files are pre-aggregated extracts, not transaction-level event records.

