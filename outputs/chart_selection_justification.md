# Chart Selection Justification

## Design Philosophy

The Executive Dashboard is designed for retail leadership who need answers to "What happened, why, and what should we do?" within 60 seconds of opening the dashboard. Every chart earns its place by answering a specific business question. Decoration, 3D effects, and excessive color variation are avoided.

---

## Chart 1: Line Chart — Monthly Sales & Profit Trend

**Business question:** How are sales and profit changing month over month? Are there seasonal peaks or concerning declines?

**Why this chart type:** Line charts are optimal for time-series data because they clearly show direction, rate of change, and inflection points. A bar chart would work but makes it harder to spot the trend visually over 24 months.

**Fields used:**
- X-axis: Order Date (aggregated to Month)
- Y-axis (left): SUM(Sales) in $M
- Y-axis (right): SUM(Profit) in $M — secondary axis for profit to preserve scale
- Color: Blue for Sales, Green for Profit

**Design principle applied:** Dual-axis with matching colors for each line — avoids confusion while enabling comparison of two different-scale measures.

**Mistake avoided:** Avoided starting the Y-axis at a non-zero value (which would exaggerate variance) and avoided a stacked bar chart (which conflates the two measures).

---

## Chart 2: Horizontal Bar Chart — Sales & Profit by Region

**Business question:** Which regions are generating the most sales and profit? Are all regions near target margin?

**Why this chart type:** Horizontal bar charts are ideal for comparing discrete categories (regions) with clear magnitude. Horizontal orientation accommodates label readability. Using grouped bars allows simultaneous comparison of sales and profit.

**Fields used:**
- Y-axis: Region
- X-axis: SUM(Sales) and SUM(Profit)
- Color: Blue for Sales, Green for Profit

**Design principle applied:** Sorted by sales descending so the largest region appears at the top — reduces cognitive load when scanning.

**Mistake avoided:** Did not use a pie chart, which would make relative magnitude comparison difficult and is inappropriate for more than 4 categories.

---

## Chart 3: Bar Chart — Profit Margin by Category vs Target

**Business question:** Which categories meet the 15% profit margin target? Which are underperforming?

**Why this chart type:** A single-measure bar chart with a reference line is the clearest way to show a metric against a benchmark. The eye immediately spots which bars fall below the reference line.

**Fields used:**
- X-axis: Category
- Y-axis: Profit Margin %
- Color: Green (above target), Amber (5–15%), Red (below 5%)
- Reference line: 15% target

**Design principle applied:** Traffic light color encoding (green/amber/red) provides an at-a-glance health signal without requiring the viewer to read exact numbers first.

**Mistake avoided:** Avoided a stacked bar showing sales and profit side-by-side (which requires mental division to compute margin); instead computed margin directly as a calculated field.

---

## Chart 4: Sub-Category Profit Bar Chart (Horizontal, Sorted)

**Business question:** Which sub-categories are the most and least profitable? Where should leadership focus investment or take corrective action?

**Why this chart type:** A sorted horizontal bar chart allows direct magnitude comparison across 13 sub-categories. Sorting by profit value immediately shows the profit distribution — the Pareto pattern is instantly visible.

**Fields used:**
- Y-axis: Sub-Category (sorted by profit ascending, so top items appear at right)
- X-axis: SUM(Profit)
- Color: Green (>$1M), Amber ($400K–$1M), Light Blue (lower)

**Design principle applied:** Sorted order + value labels on every bar eliminates need for gridline-reading. Color thresholds reinforce the ranking visually.

**Mistake avoided:** Did not use a treemap (which distorts perception of relative sizes for small categories) or a scatter plot (which adds unnecessary complexity when the sole metric is profit).

---

## Chart 5: Bar Chart — Discount Level vs Average Profit

**Business question:** How does discount depth affect profitability? Are there discount tiers that destroy value?

**Why this chart type:** A discrete bar chart with pre-bucketed discount levels is clearer than a scatter plot for this executive audience because it reduces noise and communicates a clean message: "as discounts increase, profit falls." The single axis makes magnitude comparison trivial.

**Fields used:**
- X-axis: Shipping Delay Bucket (calculated field grouping discount levels)
- Y-axis: AVG(Profit)
- Color: Green (high profit), Amber (moderate), Red (loss)

**Design principle applied:** Color-coded bars + reference line at $0 (break-even) immediately highlights the danger zone. No legend needed — colors are self-explanatory.

**Mistake avoided:** Avoided a scatter plot of raw Discount vs. Profit (which produces an unreadable cloud of 4,200 points). Bucketing pre-aggregates the signal.

---

## Chart 6: Dual-Axis Chart — Shipping Mode Delivery Days & Return Rate

**Business question:** Which shipping modes are slow, and does slow shipping cause higher returns?

**Why this chart type:** A dual-axis combination (bar for delivery days, line for return rate) allows simultaneous comparison of two related metrics. The correlation between delivery time and return rate is the key question, and two Y-axes let both metrics use appropriate scales.

**Fields used:**
- X-axis: Ship Mode
- Left Y-axis (bars): AVG(Delivery Days)
- Right Y-axis (line + markers): Return Rate %
- Color: Blue for bars, Red for return rate line

**Design principle applied:** Consistent color-to-metric mapping (blue = operational metric, red = risk metric) matches the color system used throughout the dashboard.

**Mistake avoided:** Did not use a scatter plot (ship mode is nominal, not continuous). Avoided dual-bar which would require readers to mentally separate two overlapping bars.

---

## Chart 7: Heatmap — Orders by Region × Segment

**Business question:** Is segment distribution balanced across regions, or are some region-segment combinations overly concentrated?

**Why this chart type:** A heatmap (color-encoded crosstab) is ideal for visualizing a matrix of two categorical variables. The color gradient immediately reveals which cells are hot (high volume) vs cool (low volume).

**Fields used:**
- Rows: Region
- Columns: Customer Segment
- Color: Blue gradient (darker = more orders)
- Values: Order count shown as text in each cell

**Design principle applied:** Showing both the color gradient AND the exact number in each cell satisfies both "quick scan" and "precision read" needs simultaneously.

**Mistake avoided:** Did not use a grouped bar chart (12 bars for 4 regions × 3 segments creates visual clutter). The heatmap condenses the same information into a compact 4×3 grid.

---

## Chart 8: Scatter Plot — Sales vs. Margin by Sub-Category

**Business question:** Which sub-categories have both high sales volume AND high profit margin? Which are large but low-margin?

**Why this chart type:** A scatter plot is the correct choice when the insight lies in the relationship between two continuous variables for multiple entities. The quadrant structure (high/high, high/low, low/high, low/low) helps leadership prioritize attention.

**Fields used:**
- X-axis: SUM(Sales) in $M
- Y-axis: Profit Margin %
- Size: Number of orders
- Color: Green-Yellow-Red gradient (margin level)
- Label: Sub-category name on each point

**Design principle applied:** Size encodes order volume as a third dimension without adding axis clutter. Labels on all points are feasible because there are only 13 sub-categories.

**Mistake avoided:** Did not use a bar chart for this insight (which cannot simultaneously show two metrics and a third size dimension). Avoided including individual order-level data points which would create an unreadable cloud.

---

## Dashboard Layout Principles

1. **KPI cards at top:** Leadership checks headline numbers first — revenue, profit, margin, return rate. These appear before any charts.
2. **Most important chart (sales trend) gets the most space:** 2-column width in row 2.
3. **Charts flow left-to-right, general-to-specific:** Trend → Region → Category → Sub-category (increasing granularity).
4. **Consistent color system across all charts:** Blue = Sales/volume | Green = Positive/above target | Amber = Monitor/moderate | Red = Risk/below target.
5. **Every chart has a business-language title** (not "Chart 1" or field names), making the dashboard readable without a guide.
6. **Filters at top** of the dashboard for Region, Category, Segment, Ship Mode, Campaign Channel — the five most actionable dimensions for leadership questions.
