# Primealete — Nutrition Subscription & Customer Retention Analysis

A business intelligence project analyzing subscription behavior, recurring revenue, customer spending, meal-category performance, discount usage, and retention trends for a meal-prep subscription company. Built across a full end-to-end workflow using Excel, MySQL, and Power BI.

**Tools:** Microsoft Excel · MySQL · MySQL Workbench · Power BI Desktop

---

## Project Overview

The project evaluated business performance using a structured transactional dataset of 550+ order records with anonymized Customer IDs, meal details, pricing, subscription status, discount codes, and plan-tier information. The same source data was used across two technical layers — MySQL for storage and SQL analysis, and Power BI for dashboarding and visual reporting — creating a clean, realistic data pipeline from source to insight.

---

## Dataset Structure

The source dataset was built in Excel as a single transactional table, exported as CSV, and imported into MySQL. Each row represents one order record.

| Field Group | Examples | Purpose |
|---|---|---|
| Identifiers | Order_ID, Customer_ID | Track unique transactions and anonymized customer activity |
| Product Fields | Meal_Name, Meal_Category, Quantity | Analyze demand, meal mix, and category trends |
| Pricing Fields | Price_Per_Meal, Total_Order_Value, Discount_Code | Evaluate spend, discounts, and revenue impact |
| Subscription Fields | Order_Type, Subscription_Plan | Compare recurring plans against one-time purchases |
| Time Fields | Order_Date | Review purchase timing and trend movement over time |

---

## Workflow

**Excel** — Dataset was cleaned and structured. Customer names were replaced with anonymized IDs, pricing values were standardized, subscription-tier labels were normalized, and the sheet was prepared for CSV export.

**MySQL / MySQL Workbench** — CSV was imported into a MySQL database. SQL queries were written to answer specific business questions about revenue, customer behavior, and product performance.

**Power BI** — Connected directly to the MySQL database (not the raw Excel file) to build the dashboard. This created a clean three-layer workflow: Excel as source, MySQL as the analytical layer, Power BI as the reporting layer.

---

## SQL Analysis

| Business Question | Query Logic |
|---|---|
| Revenue by subscription tier | SUM of Total_Order_Value grouped by Subscription_Plan, filtered to subscription orders only |
| One-time vs. subscription comparison | COUNT, AVG, and SUM of orders grouped by Order_Type |
| Customer spending analysis | COUNT of orders and SUM of spend per Customer_ID, ordered by total spend |
| Meal-category revenue | SUM of Total_Order_Value grouped by Meal_Category |

```sql
-- Revenue by subscription tier
SELECT Subscription_Plan, SUM(Total_Order_Value) AS Total_Revenue
FROM Orders
WHERE Order_Type = 'Subscription'
GROUP BY Subscription_Plan
ORDER BY Total_Revenue DESC;

-- Customer spending
SELECT Customer_ID, COUNT(Order_ID) AS Order_Count, SUM(Total_Order_Value) AS Total_Spend
FROM Orders
GROUP BY Customer_ID
ORDER BY Total_Spend DESC;

-- Meal-category revenue
SELECT Meal_Category, SUM(Total_Order_Value) AS Category_Revenue
FROM Orders
GROUP BY Meal_Category
ORDER BY Category_Revenue DESC;

-- One-time vs. subscription
SELECT Order_Type, COUNT(Order_ID) AS Orders,
       AVG(Total_Order_Value) AS Avg_Order_Value,
       SUM(Total_Order_Value) AS Revenue
FROM Orders
GROUP BY Order_Type;
```

---

## Power BI Dashboard

The dashboard was connected to the MySQL database and includes:

- **KPI cards** for recurring revenue, average order value, repeat purchase count, and plan mix
- **Subscription-tier comparison** bar chart showing revenue by plan level
- **One-time vs. subscription** revenue comparison visual
- **Meal-category revenue** breakdown across all menu groups
- **Customer spending summary** highlighting top buyers and repeat behavior
- **Discount usage analysis** showing the revenue impact of promotional codes
- **Slicers** for Order Type, Subscription Plan, and Meal Category

---

## Key Findings

- The subscription model provided more consistent and predictable revenue visibility than one-time purchases
- Tier-level revenue comparison identified which subscription plans were strongest performers
- Customer spending analysis surfaced repeat buyers with the highest lifetime value
- Meal-category analysis revealed which menu groups drove the most revenue
- Discount usage patterns showed where promotional codes had the greatest impact on order behavior

---

## Business Recommendations

- **Subscription strategy:** Focus retention efforts on the highest-revenue tiers; develop targeted upsell paths for lower-tier subscribers
- **Promotional timing:** Align discount codes to periods of lower order volume to drive activity without eroding margin during peak periods
- **Menu prioritization:** Increase availability and promotion of top-performing meal categories
- **Customer retention:** Use repeat-purchase data to identify at-risk customers and trigger re-engagement campaigns before churn occurs

---

## Files

| File | Description |
|---|---|
| `Primealete_Project_Dataset.xlsx` | Source dataset used for the project |
| `Primealete_Project_Dataset.csv` | CSV export used for MySQL import |
| `Primealete_Project.docx` | Full project guide and build summary |

---

## Author

**Ibrahim Ammar** — [github.com/imammar1](https://github.com/imammar1)
