# Looker Studio Report – Sales Dashboard

This Looker Studio report connects to the **gold layer** outputs in `data/gold/`:

- `sales_by_customer.csv`
- `sales_by_geo.csv`
- `sales_over_time.csv`

## Live Report

View-only link:  
https://lookerstudio.google.com/reporting/63f5c462-c64e-476e-958c-4ef016af7ec7

## Data Model

- **sales_by_customer** – grain: customer  
  Columns: `CustomerId`, `CustomerName`, `City`, `CountryName`, `Region`, `TotalQuantity`, `DistinctOrders`.

- **sales_by_geo** – grain: country/region  
  Columns: `CountryName`, `Region`, `TotalQuantity`.

- **sales_over_time** – grain: day  
  Columns: `OrderDate`, `TotalQuantity`.

## Report Pages

1. **Customer Performance**
   - Table / bar chart by `CustomerName` with `TotalQuantity`, `DistinctOrders`.
   - Slicers: `CountryName`, `Region`.

2. **Sales by Geography**
   - Map by `CountryName` with `TotalQuantity`.
   - Supporting bar by `Region`.

3. **Sales Over Time**
   - Line chart of `TotalQuantity` over `OrderDate`.
   - Optional filters: `Region`, `CountryName`.

## Architecture Mapping

- **Bronze**: raw JSON → Parquet (`data/bronze/`).
- **Silver**: dimensional model (`dim_country`, `dim_customer`, `dim_product`, `fact_sales_enriched`) in `data/silver/`.
- **Gold**: aggregated CSVs (`data/gold/*`) used directly by Looker Studio (and Power BI).

The same gold-layer tables can be consumed by other BI tools without changing the upstream pipeline.
