# BP Wayne Truck Stop — Sales & Traffic Performance Dashboard

A business analytics project modeling 30 days of operational activity for BP Wayne Truck Stop and its adjacent restaurant tenant. The project covers the full pipeline from raw dataset construction in Excel to a polished, interactive Power BI dashboard with KPI tracking, trend analysis, and operational recommendations.

**Tools:** Microsoft Excel · Power BI Desktop

---

## Project Overview

The station serves a steady mix of fuel customers, inside-store shoppers, and restaurant traffic throughout the day. This project builds a realistic hourly dataset for a 30-day period, analyzes it across multiple business dimensions, and produces a dashboard that communicates traffic patterns, sales behavior, peak-period pressure, and staffing and restocking recommendations.

The final output is a portfolio-ready dashboard that demonstrates operational thinking, data modeling, and business intelligence skills.

---

## Dataset Structure

Built in Excel with one row per hour per day, covering 720 hourly records across the full 30-day period. Each row captures:

| Column | Description |
|---|---|
| Date | Day in the 30-day period |
| Day | Day of the week |
| Day Type | Weekday / Saturday / Sunday |
| Hour | Hour of the day |
| Store Transactions | Number of store customers that hour |
| Restaurant Orders | Number of restaurant orders that hour |
| Fuel Sales | Fuel revenue for the hour |
| Store Sales | Inside-store revenue for the hour |
| Total Sales | Fuel Sales + Store Sales |
| Avg Basket Value | Average spend per store customer |
| Inventory Risk | Low / Medium / High |
| Peak Hour | Yes / No flag for high-demand windows |
| Category Focus | Drinks / Snacks / Cigarettes / Hot Food / Misc |

**Core formulas:**
- Store Sales = Store Transactions × Avg Basket Value
- Total Sales = Fuel Sales + Store Sales
- Inventory Risk and Peak Hour flags assigned based on demand thresholds per time window

---

## Traffic & Demand Assumptions

- **Sunday** is the strongest day for restaurant demand
- **Saturday** is busy but does not exceed Sunday
- **Weekdays** show consistent spikes at 12 PM, 3 PM, 5 PM, and 11 PM–12 AM
- **Store sales** remain steady throughout the day driven by drinks, snacks, and cigarettes
- **Average basket value** modeled between $10–$20 per store customer

---

## KPIs Tracked

| KPI | What It Measures |
|---|---|
| Total Sales | Overall business volume across the 30-day period |
| Total Store Transactions | Cumulative store customer count |
| Total Restaurant Orders | Cumulative restaurant order count |
| Average Basket Value | Average in-store spend per customer |
| Peak Hour Count | Number of hours flagged as high-demand periods |
| High Inventory Risk Count | Number of hours flagged with High restocking pressure |

---

## Power BI Dashboard

The dashboard was built in Power BI Desktop using the Excel file as the data source. It includes:

- **KPI cards** across the top for all six business metrics
- **Sales by Hour** chart showing demand timing throughout the day
- **Restaurant Orders by Hour** chart for tenant-specific traffic analysis
- **Day Type Comparison** visual contrasting Weekday, Saturday, and Sunday behavior
- **Category Sales Mix** breakdown across Drinks, Snacks, Cigarettes, Hot Food, and Misc
- **Slicers** for Day, Day Type, and Category Focus for interactive filtering

---

## Key Findings

- Sunday consistently produced the highest restaurant order volume of the week
- Weekday demand followed a predictable four-spike pattern: lunch, mid-afternoon, early evening, and late night
- Drinks, snacks, and cigarettes maintained steady store sales across all day types and hours
- Peak-hour windows drove the highest concentration of High inventory risk flags
- Saturday was the second-busiest day but did not exceed Sunday restaurant demand

---

## Business Recommendations

- **Staffing:** Schedule additional staff around the 12 PM, 3 PM, 5 PM, and 11 PM windows on weekdays and throughout Sunday
- **Restocking:** Align restocking cadence to pre-peak windows, particularly before midday and early evening rushes
- **Product placement:** Prioritize front-of-store placement for drinks, snacks, and cigarettes given their consistent contribution to basket value
- **Restaurant coverage:** Ensure full restaurant staffing on Sundays given peak order volume

---

## Files

| File | Description |
|---|---|
| `BP_Wayne_Truck_Stop_Dataset.xlsx` | Full 30-day hourly dataset used as the Power BI data source |
| `BP_Wayne_Truck_Stop_Sales_Traffic_Performance_Dashboard.pbix` | Power BI dashboard file |
| `BP_Wayne_Truck_Stop_Project.docx` | Full project guide and build summary |

---

## Author

**Ibrahim Ammar** — [github.com/imammar1](https://github.com/imammar1)
