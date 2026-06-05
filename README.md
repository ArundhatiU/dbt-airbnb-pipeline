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

## Project Architecture
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

> DAG screenshot will be added after dbt docs are generated.

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

## Learnings

- Hands-on experience with dbt Core project structure and best practices
- Snowflake warehouse configuration and cost optimization basics
- Writing modular, testable SQL using dbt's ref() and source() functions
- Understanding of analytics engineering workflows end to end
