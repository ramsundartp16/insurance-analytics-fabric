# Insurance Analytics on Microsoft Fabric

## Project Overview
This project demonstrates an end-to-end insurance analytics pipeline built using **Microsoft Fabric**.  
The goal of the project is to ingest historical and incremental insurance data, transform it using a medallion architecture, model it into business-friendly structures, and visualize insights using **Power BI**.

The project simulates a real-world scenario where a data engineering team delivers analytics-ready data to analysts and business users within a short timeline.

---

## Business Objective
Provide insights into:
- Active policies and customers
- Premium collections and payments
- Claims and approved claims
- Loss ratio trends
- Performance breakdown by policy type and region

---

## Architecture Overview
The solution follows a **Bronze → Silver → Gold** medallion architecture within Microsoft Fabric:

<img width="773" height="65" alt="image" src="https://github.com/user-attachments/assets/6182962d-4a0a-41ea-92e4-651beeda1aeb" />


- **Source:** CSV, JSON, Parquet, API-style synthetic insurance data  
- **Ingestion:** Incremental batch ingestion into OneLake  
- **Bronze:** Raw Delta tables stored in Fabric Lakehouse  
- **Silver:** Cleaned and standardized data using Spark notebooks  
- **Gold:** Star schema with fact and dimension tables  
- **Consumption:** Power BI semantic model and dashboard

---

## Technology Stack
- **Microsoft Fabric**
  - OneLake / Lakehouse
  - Spark Notebooks (PySpark)
  - Data Factory Pipelines
  - Semantic Model (DirectLake)
- **Power BI**
- **Delta / Parquet**
- **GitHub** (documentation & versioning)

---

## Data Modeling
The Gold layer uses a **star schema**:
- **Fact tables:** Premium payments, claims
- **Dimension tables:** Date, Customer, Agent, Policy

This structure enables efficient analytics and reporting.

---

## Dashboard
The Power BI dashboard provides:
- Executive KPIs
- Time-based trends
- Breakdown analysis by policy type and region
- Year-based filtering

The dashboard is built on top of a Fabric semantic model using DirectLake.

---

## Project Structure

## Project Structure

```text
notebooks/
├── source_data_generation/
│   ├── 01_Source_Data_Generation.ipynb
│   ├── 02_Source_Policies.ipynb
│   ├── 03_Source_Premiums.ipynb
│   └── 04_Source_Claims.ipynb
├── bronze_ingestion/
│   └── 05_Bronze_Ingestion.ipynb
├── silver_transformation/
│   └── 06_Silver_Transformations.ipynb
└── gold_modeling/
    └── 07_Gold_Fact_Dim_Modeling.ipynb
power_bi/
├── Insurance_Dashboard_Measures.png
├── Insurance_Performance_Breakdown.png
├── Insurance_Performance_Dashboard.png
├── Insurance_Performance_KPI.png
├── Insurance_Performance_Trend.png
└── Insurance_Semantic_Model.png
architecture/
└── Insurance_Performance_e2e_architecture.png
README.md

```
---

## Notes
- Data used in this project is **synthetically generated** for learning and demonstration purposes.
- The project focuses on **architecture, data flow, and modeling practices**, not on specific business outcomes.
- The pipeline supports **incremental data processing**.

---

## Author
Ram Sundar



