# AI/BI Databricks + Genie Demo (Superstore)

## Overview
This repository demonstrates an end-to-end **AI-powered Business Intelligence workflow** using **Azure Databricks**, the **Medallion architecture (Bronze → Silver → Gold)**, and **Databricks Genie** for conversational analytics.
The demo uses the Superstore dataset to show how governed data preparation enables natural-language insights without manual SQL.

## Architecture
The solution follows a layered, analytics-ready design:

- **Bronze**: Raw ingestion from Azure Data Lake Gen2
- **Silver**: Data cleansing, schema standardization, and normalization
- **Gold**: Business-ready semantic layer enriched with derived metrics
- **Genie**: Natural language analytics over the Gold layer

This structure ensures data quality, governance, and accurate AI-driven insights.

## What This Demo Covers
- Secure data access from **ADLS Gen2** using Databricks
- Bronze ingestion and validation (row counts, null checks, duplicates)
- Silver transformations:
  - Column standardization
  - Data type enforcement
  - Normalization to a clean order–product grain
- Gold layer enrichment with business logic (profit flag)
- Column-level metadata to support BI tools and Genie
- Genie usage for conversational analytics on governed data

## Databricks Notebook
**AI_BI_Databricks_Genie_Demo.ipynb**

The notebook walks through:
1. Data ingestion into Bronze
2. Data quality checks
3. Silver layer transformations
4. Gold layer semantic preparation
5. Validation queries for analytics readiness

The notebook is designed to be readable and reviewable outside Databricks when exported as `.ipynb`.

## Genie (AI-Powered BI)
Databricks Genie was used to explore the Gold layer using natural-language questions such as:
- Which sub-categories are unprofitable?
- How does profit vary by region and category?
- What is the impact of discounts on profitability?
- Which products consistently generate losses?

Genie dynamically translates these questions into SQL against the curated Gold layer, enabling conversational analytics without manual query writing.
Representative Genie results are captured as screenshots for reference.

## Repository Structure
```
ai-bi-genie-demo/
├── AI_BI_Databricks_Genie_Demo.ipynb
├── README.md
├── data/
│   └── superstore.csv
└── screenshots/
    └── genie_*.png / genie_*.gif
```

## Notes
- Genie conversations are session-based and not persisted; insights are documented instead of exporting chat history.
- Secrets and credentials are managed using Databricks secret scopes and are not exposed in this repository.
- The included CSV is for reference; ingestion in the demo uses ADLS Gen2.

## Use Case
This demo is intended for:
- AI/BI capability overviews
- Internal team knowledge sharing
- Architecture walkthroughs
- Stakeholder demos of conversational analytics

## Main takeaways
This project demonstrates how a well-designed Medallion architecture enables reliable, governed analytics and unlocks AI-powered insights through Databricks Genie, showing that conversational BI works best when built on clean, business-ready Gold data rather than raw or loosely prepared datasets.
