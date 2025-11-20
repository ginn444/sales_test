# 🧾 Sales Dashboard Project

Build a Power BI Dashboard while demonstrating how to build data pipelines.

## 🎶 Stakeholder Problem Statement
- Stakeholder wants to see sales by customer.
- Stakeholder wants to see sales by geo-location.

## 🚀 TODOS

- Data wrangling / EDA.
- Load and preprocess data in data pipelines.
- Build bronze, silver, gold medallion layers. Nothing too crazy needed.
- Build a Power BI Dashboard utilizing gold layer.

## 📦 Project Tech Stack
- uv
- Python
    - PySpark, Polars, Pandas
- Database
    - DuckDB or something similar to demonstrate object storage for use in Power BI.
- Orchestration
    - Not needed for this project, but we do use Databricks and Prefect.

## 🏗️ Architecture Note

In production this would map to PySpark tables in Databricks with Unity Catalog; here I simulate it locally with Polars + DuckDB.


## 🛠️ Setup Instructions

1. **Clone the repo**
   ```bash
   git clone https://github.com/timmyjl12/sales_test.git
   cd sales_test
   ```
