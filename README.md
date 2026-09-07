# Bank Loan Default Risk & Portfolio Analytics Pipeline

## Project Overview
This project builds a complete Data Engineering solution for a financial institution. It ingests raw borrower data, credit bureau metrics, and loan repayment history, cleans and enriches the data, calculates credit risk scores and delinquency buckets, and produces business-ready tables for portfolio risk monitoring.

## Architecture (Medallion)
| Layer   | Description |
|---------|-------------|
| **Bronze** | Raw ingestion from CSV files: `borrowers.csv`, `credit_bureau.csv`, `loan_repayments.csv` → stored as Delta tables. |
| **Silver** | Data cleaning, deduplication, type casting, date formatting, and joins to create an enriched `loan_fact` table. |
| **Gold**   | Business aggregates: Daily default rates, Risk score distribution, Delinquency buckets (30/60/90+ DPD), Portfolio performance. |

## Tech Stack
- Databricks (PySpark, Spark SQL)
- Delta Lake
- Google BigQuery
- Looker Studio

## Key Features
- ✅ Automated Data Quality Checks
- ✅ Credit Risk Scoring using PySpark Window Functions (RANK, LAG/LEAD)
- ✅ Delinquency Bucketing (30, 60, 90+ days past due)
- ✅ Portfolio Aggregations and Executive Dashboard

## Project Structure
- `01_Bronze_ingestion.py`
- `02_Silver_cleaning.py`
- `03_Gold_aggregations.py`
- `04_BigQuery_export.py`
