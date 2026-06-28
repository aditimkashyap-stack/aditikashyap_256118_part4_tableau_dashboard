
# Part 4: Tableau Executive Dashboard & Data Storytelling

## Business Problem Summary

A retail chain leadership team needs an executive dashboard to monitor and improve sales performance, profitability, customer segment behavior, category performance, shipping efficiency, discount impact, and return patterns. The dashboard enables data-driven decisions about where to invest, what to fix, and what risks to monitor.

---

## Dataset Description

**File:** `data/dashboard_sales_data.xlsx`  
**Rows:** 4,200 orders | **Period:** Jan 2024 – Dec 2025  
**Columns:** 20

| Column | Type | Description |
|---|---|---|
| order_id | Categorical | Unique order identifier |
| order_date | Date | Date order was placed |
| ship_date | Date | Date order was shipped |
| customer_id | Categorical | Unique customer identifier |
| customer_segment | Categorical | Consumer / Corporate / Home Office |
| region | Categorical | North / South / East / West |
| state | Categorical | Indian state |
| city | Categorical | City of delivery |
| category | Categorical | Furniture / Office Supplies / Technology |
| sub_category | Categorical | 13 sub-categories |
| product_name | Text | Product name |
| ship_mode | Categorical | Same Day / First Class / Second Class / Standard Class |
| sales | Numeric | Order revenue ($) |
| quantity | Numeric | Units ordered |
| discount | Numeric | Discount rate (0–1) |
| profit | Numeric | Net profit ($) |
| return_flag | Binary (0/1) | 1 if order was returned |
| delivery_days | Numeric | Days from order to delivery |
| customer_rating | Numeric | Satisfaction score (1–5); 32 missing |
| campaign_channel | Categorical | Organic / Paid / Email / Social / Referral; 24 missing |

---

## Tableau Workbook Description

**File:** `tableau/executive_dashboard.twbx`  
A Tableau Packaged Workbook (.twbx) containing:
- Embedded data CSV
- 7 worksheet views
- 1 executive dashboard sheet
- 5 calculated fields
- 5 interactive filters

### Worksheets Included
1. Sales Trend — Monthly sales and profit over time
2. Regional Performance — Sales, profit, and margin by region
3. Category Profitability — Category and sub-category profit analysis
4. Customer Segment — Segment comparison (sales, returns, AOV)
5. Shipping Performance — Delivery time and return rate by ship mode
6. Discount vs Profit — Discount depth and average profit relationship
7. Return Analysis — Return rate by category, segment, and region

---

## Calculated Fields Created

| Field | Formula | Business Purpose |
|---|---|---|
| Profit Margin | `SUM([profit]) / SUM([sales])` | Measures profitability efficiency |
| Cost | `[sales] - [profit]` | Derives implied COGS |
| Avg Order Value | `SUM([sales]) / COUNTD([order_id])` | Tracks average transaction size |
| Return Rate | `SUM([return_flag]) / COUNT([order_id])` | Monitors return risk |
| Shipping Delay Bucket | `IF [delivery_days] <= 1 THEN "Express" ELSEIF [delivery_days] <= 3 THEN "Fast" ELSEIF [delivery_days] <= 5 THEN "Standard" ELSE "Delayed" END` | Segments delivery performance |

---

## Dashboard Components

**KPI Cards (7):**
- Total Sales: $217.0M
- Total Profit: $33.3M
- Profit Margin: 15.3%
- Total Orders: 4,200
- Return Rate: 4.5%
- Avg Delivery Days: 3.6
- Customer Rating: 4.06/5

**Charts (6):**
1. Monthly Sales & Profit Trend (line/area chart with moving average)
2. Sales & Profit by Region (grouped horizontal bar)
3. Profit Margin by Category (horizontal bar with 15% target reference line)
4. Sub-Category Profit (sorted horizontal bar, color-coded)
5. Discount Level vs Average Profit (bar chart showing profit erosion)
6. Ship Mode: Avg Days & Return Rate (dual-axis: bar + line)

---

## Filters and Interactions

**Filters:**
- Region (North / South / East / West)
- Category (Furniture / Office Supplies / Technology)
- Customer Segment (Consumer / Corporate / Home Office)
- Ship Mode (Same Day / First Class / Second Class / Standard Class)
- Campaign Channel (Organic / Paid / Email / Social / Referral)

**Dashboard Actions:**
- Clicking a region bar filters all other views to that region
- Clicking a category filters sub-category and trend views accordingly

---

## Key Business Insights

1. Technology generates 84% of total profit at 18.2% margin
2. Furniture underperforms at 6.9% margin (target: 15%)
3. Discounts above 30% generate net losses (avg –$1,601/order)
4. Same Day shipping has the lowest return rate (2.1% vs 5.0% Standard Class)
5. Home Office has the highest return rate at 6%
6. South region leads in sales volume at $64.7M
7. Copiers, Accessories, and Phones are the most profitable sub-categories
8. Standard Class dominates (58% of orders) but is the slowest and highest-risk mode

---

## Dashboard Story Summary

The retail chain is fundamentally healthy: 15.3% overall profit margin just above target, and strong Technology performance. However, three structural risks require leadership attention: Furniture's chronic 6.9% margin, discount tiers above 20% destroying profit, and Home Office return rates running 50% above other segments. The biggest opportunity is the discount policy reform: eliminating 31%+ discount authorizations would immediately recover ~$102K in annual losses with no apparent volume downside.

---

## Assumptions and Limitations

- `customer_rating` has 32 missing values (0.8%); excluded from averages where missing
- `campaign_channel` has 24 missing values (0.6%); shown as "Unknown" in channel analysis
- Profit margin calculations use SUM(profit)/SUM(sales) at each level of aggregation to avoid distortion from order-level averaging
- Return rate is measured per order, not per customer — one customer with multiple returns would appear as multiple return events
- Delivery days represent calendar days, not business days
- All currency figures are in INR unless otherwise specified (dataset uses Indian cities/states)

---

## Screenshots Included

| File | Description |
|---|---|
| `screenshots/full_dashboard.png` | Complete executive dashboard with all KPIs, trend, regional, category, sub-category, discount, and shipping charts |
| `screenshots/sales_trend_view.png` | Monthly trend, quarterly comparison, segment trends, campaign channel breakdown |
| `screenshots/regional_performance_view.png` | Sales, margin, order heatmap, return rate, AOV, and category mix by region |
| `screenshots/category_profitability_view.png` | Category profit, margin vs target, sub-category ranking, scatter analysis, heatmap, return rate |
| `screenshots/filter_interaction_view.png` | Demonstration of Technology + South + Corporate filter combination with all views updated |
