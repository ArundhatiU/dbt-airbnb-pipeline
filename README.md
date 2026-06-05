# Airbnb Analytics Pipeline

An end-to-end analytics pipeline built on dbt Core and Snowflake, transforming 
raw Airbnb data into structured, query-ready models for pricing, availability, 
and host performance analysis.
---

## Tech Stack

| Layer | Tool |
|---|---|
| Data Warehouse | Snowflake |
| Transformations | dbt Core |
| Language | SQL |
| Version Control | GitHub |

---
## Pipeline Architecture

```plaintext
Raw Airbnb Data (Snowflake source tables)
        │
        ▼
  Staging Models        ← Light cleaning, renaming, type casting
        │
        ▼
  Intermediate Models   ← Business logic, joins
        │
        ▼
  Mart Models           ← Final analytics-ready tables
```
---

## Data Models

### Staging
- `stg_listings` — cleaned listings data (price, room type, neighbourhood)
- `stg_reviews` — cleaned reviews with host and listing references
- `stg_hosts` — host-level attributes

### Marts
- `mart_listings_summary` — aggregated listing metrics by neighbourhood
- `mart_host_performance` — host-level review counts and average ratings

> Model names are placeholders — update with your actual model names.

---

## dbt Features Used

- **Sources** — defined raw Snowflake tables with freshness checks
- **Tests** — `not_null`, `unique`, `accepted_values` on key columns
- **Documentation** — `description` fields on models and columns
- **Refs** — dependency management across staging and mart layers

---
## How to Run

### Prerequisites
- Snowflake account with warehouse, database, and schema configured
- dbt Core installed (`pip install dbt-snowflake`)
- `profiles.yml` configured with your Snowflake credentials

### Steps

```bash
# Clone the repo
git clone https://github.com/ArundhatiU/airbnb-analytics-pipeline.git
cd airbnb-analytics-pipeline

# Install dbt dependencies
dbt deps

# Run all models
dbt run

# Run tests
dbt test
```

## Learnings

- Hands-on experience with dbt Core project structure and best practices
- Snowflake warehouse configuration and cost optimization basics
- Writing modular, testable SQL using dbt's ref() and source() functions
- Understanding of analytics engineering workflows end to end
