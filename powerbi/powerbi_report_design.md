# Power BI Report Design – Sales Dashboard

This report is intended to connect directly to the **gold layer** outputs in `data/gold`:

- `sales_by_customer.csv`
- `sales_by_geo.csv`
- `sales_over_time.csv`

## Data Model

- `sales_by_customer` – grain: customer
- `sales_by_geo` – grain: country/region
- `sales_over_time` – grain: day

These tables can be loaded as separate tables in Power BI (no complex relationships required, since they are already aggregated).

## Report Pages

1. **Customer Performance**
   - Visuals:
     - Table or bar chart by `CustomerName` with `TotalQuantity`, `DistinctOrders`.
     - Optional slicers: `CountryName`, `Region`.

2. **Sales by Geography**
   - Visuals:
     - Map or filled map using `CountryName` (or `CountryCode`) and `TotalQuantity`.
     - Supporting bar chart by `Region`.

3. **Sales Over Time**
   - Visuals:
     - Line chart with `OrderDate` on the axis and `TotalQuantity` as the measure.
     - Optional slicers: `Region`, `CountryName`.
