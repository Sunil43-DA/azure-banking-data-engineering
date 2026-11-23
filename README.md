
# Azure Banking Data Engineering Platform

## Project Overview

An end-to-end Azure Data Engineering project designed to simulate a modern banking data platform.

The project demonstrates batch and streaming data ingestion, cloud data storage, distributed processing, data transformation, data modelling, security, monitoring and business intelligence.

## Business Scenario

A digital banking organisation receives customer, account and transaction data from multiple sources.

The objective is to build a scalable data platform that can:

- Ingest banking data from multiple sources.
- Store raw data in Azure Data Lake Storage Gen2.
- Clean and transform data using PySpark.
- Implement Bronze, Silver and Gold architecture.
- Maintain historical records using SCD Type 2.
- Analyse suspicious transaction patterns.
- Provide business reporting through Power BI.
- Automate pipelines and monitor failures.

## Technology Stack

| Technology | Purpose |
|---|---|
| Azure Data Factory | Data ingestion and orchestration |
| ADLS Gen2 | Cloud data storage |
| Azure Databricks | Distributed data processing |
| PySpark | Data transformation |
| Azure Synapse Analytics | SQL analytics |
| Azure Event Hubs | Streaming ingestion |
| Azure Key Vault | Secrets management |
| Azure Monitor | Monitoring |
| Power BI | Data visualisation |
| Git and GitHub | Version control |

## Architecture

Source Systems
      |
      v
Azure Data Factory / Event Hubs
      |
      v
Azure Data Lake Storage Gen2
      |
      v
Bronze Layer
      |
      v
Silver Layer
      |
      v
Gold Layer
      |
      v
SQL Analytics
      |
      v
Power BI Dashboards

## Data Architecture

### Bronze Layer
Stores original source data without business transformations.

### Silver Layer
Stores cleaned, validated and deduplicated data.

### Gold Layer
Stores business-ready datasets for analytics and reporting.

## Project Modules

- [ ] Azure infrastructure setup
- [ ] ADLS Gen2 configuration
- [ ] Azure Data Factory pipelines
- [ ] Batch data ingestion
- [ ] PySpark transformations
- [ ] Incremental data loading
- [ ] SCD Type 2 implementation
- [ ] Streaming with Event Hubs
- [ ] SQL analytics
- [ ] Data quality validation
- [ ] Power BI dashboards
- [ ] Security and monitoring
- [ ] CI/CD deployment

## Repository Structure

```text
azure-banking-data-engineering/
|
|-- docs/
|-- architecture/
|-- data/
|-- pipelines/
|-- notebooks/
|-- src/
|-- sql/
|-- screenshots/
|-- README.md
```

## Data Privacy

This project uses synthetic banking data for learning and demonstration purposes.

No real customer financial information, credentials or sensitive banking records are stored in this repository.

## Learning Objectives

- Understand Azure Data Engineering architecture.
- Build multi-tool data pipelines.
- Learn production-style data engineering practices.
- Develop troubleshooting and optimisation skills.
- Prepare for Azure Data Engineer interviews.

## Project Status

Currently in the infrastructure setup phase.

More implementation details will be added as the project progresses.
