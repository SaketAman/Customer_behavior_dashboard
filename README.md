<img width="1122" height="632" alt="Screenshot 2026-07-21 152606" src="https://github.com/user-attachments/assets/c65dc1bc-83b6-4718-bd6e-9abf959b1249" />

# Customer Behavior.pbix — Report Documentation

## Overview
This is a single-page Power BI report titled **"Customer Behavior Data Report"**, built on one imported table: **`ecommerce_customer_churn_dataset`**. The report gives a quick visual summary of purchase behavior, customer value, and churn-related signals across demographics and geography.

- **Report tool:** Power BI (created via Power BI Service/Cloud, June 2026 release)
- **Pages:** 1 (`Page 1`, 1280 × 720)
- **Theme:** Twilight
- **Data source:** single table, `ecommerce_customer_churn_dataset`

## Data Model
The report uses one flat table with no relationships (single-table model). Fields referenced across the visuals:

| Field | Type of use |
|---|---|
| `Signup_Quarter` | Category axis |
| `Total_Purchases` | Measure (summed) |
| `Cart_Abandonment_Rate` | Measure (summed) |
| `Average_Order_Value` | Measure (summed) |
| `Gender` | Category / slicer |
| `City`, `Country` | Category / series / slicer |
| `Age` | Category axis |
| `Lifetime_Value` | Measure (summed) |

## Page Layout — "Page 1"

| Visual | Type | Fields used | Purpose |
|---|---|---|---|
| Title textbox | Text box | — | "Customer Behavior Data Report" header |
| Card | Card | Sum of `Total_Purchases` | Total purchases KPI |
| Card | Card | Sum of `Lifetime_Value` | Customer lifetime value KPI |
| Chart 1 | Clustered column | `Signup_Quarter` (category) vs Sum of `Total_Purchases` | Purchases trend by signup quarter |
| Chart 2 | Clustered column | `Gender` (category) vs Sum of `Cart_Abandonment_Rate` & Sum of `Average_Order_Value` | Cart abandonment and order value by gender |
| Chart 3 | Clustered column | `Country` / `City` (category & series) vs Sum of `Total_Purchases` | Purchases by country/city |
| Chart 4 | Clustered column | `Age` (category) vs Sum of `Total_Purchases` | Purchases by age group |
| Slicer 1 | Slicer | `Country` | Filter by country |
| Slicer 2 | Slicer | `Gender` | Filter by gender |

## How to Use This File
1. Open `Customer_behavior.pbix` in Power BI Desktop (2026 or later recommended, to match the file's creation version).
2. Use the **Country** and **Gender** slicers to filter all visuals on the page.
3. The two KPI cards at the top give at-a-glance totals for **Total Purchases** and **Lifetime Value**.
4. The four column charts break those totals down by signup quarter, gender, location, and age — useful for spotting churn-risk segments (e.g., high cart abandonment or low average order value in a given group).

## Notes
- The underlying data model is stored in Power BI's compressed internal format, so exact row-level data and DAX measure formulas aren't human-readable outside Power BI Desktop — this README reflects what's visible in the report's visual/field structure.
- No calculated measures beyond simple `Sum()` aggregations were found; all values are direct sums of source columns.
- No custom relationships were detected — the model is a single flat table.
