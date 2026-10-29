# European Power Analytics Warehouse

How much electricity does each European country consume and generate by source,
hour by hour, and what will tomorrow's load be?

An end-to-end analytics engineering project on public ENTSO-E Transparency Platform data:
ingestion in Python, modelling and testing in dbt, orchestration with Airflow,
a day-ahead load forecast, and a natural-language (text-to-SQL) layer on top.

## Scope

| Version | Target | Scope |
| --- | --- | --- |
| v1 - Warehouse | Feb 2027 | ENTSO-E API → PostgreSQL raw → dbt staging + marts → daily Airflow DAG in Docker → CI on GitHub Actions |
| v2 - Forecast | Mar 2027 | dbt project moved to Snowflake → feature mart → day-ahead load forecast per country, back-tested against a seasonal-naive baseline |
| v3 - AI layer | Apr 2027 | Text-to-SQL assistant grounded on dbt model docs, scored on 20 test questions |

Countries: 6–8 European bidding zones. Grain: hourly load and generation by source.

## Planned architecture

ENTSO-E API → Python ingest (EntsoeClient) → raw tables → dbt (staging → marts → features)
→ forecast model → forecasts table → Streamlit + text-to-SQL assistant

## Tech stack

Python · PostgreSQL · Snowflake · dbt · Airflow · Docker · GitHub Actions · Streamlit

## Status

🚧 Week 1 — repository set up. Build log and design notes to follow.
