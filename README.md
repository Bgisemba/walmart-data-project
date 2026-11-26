# Walmart End-to-End Data Engineering Project

## Overview
An end-to-end modern data engineering pipeline built for a retail (**Walmart**) use case using a **Lakehouse (Bronze, Silver, Gold)** architecture. The project covers incremental/CDC ingestion, SQL-first transformations and dimensional modeling with **dbt**, and workflow orchestration with **Apache Airflow** on **Databricks**.

## Tech Stack
- **Data Processing & Lakehouse:** Databricks, Apache Spark, Delta Lake
- **Transformations & Modeling:** dbt (with Jinja, ephemeral models, tests, and snapshots)
- **Orchestration:** Apache Airflow (Dockerized)
- **Sources:** Hosted Postgres / Agentic Database (`Neon`) 
- **Version Control & IDE:** Git, GitHub, VS Code, Python

## Architecture & Pipeline Layers
1. **Ingestion & Bronze Layer:**
   - Pulls source database tables incrementally/via CDC into **Databricks Delta tables** using pipelines and scheduled jobs.
2. **Transformation & Silver Layer (dbt):**
   - Cleans and joins datasets in **dbt** to construct a **One Big Table (OBT)** using ephemeral models, Jinja logic, and data quality tests.
3. **Serving & Gold Layer (dbt):**
   - Implements dimensional modeling (**star schema**) and **SCD Type 2** historical tracking using **dbt snapshots**.
4. **Orchestration (Apache Airflow):**
   - Orchestrates pipeline steps and granular dbt commands (such as source freshness checks and model runs) via Airflow DAGs.

