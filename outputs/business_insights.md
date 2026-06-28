# Business Insights from Executive Dashboard

## Calculated Fields Created

| Field | Formula | Purpose |
|---|---|---|
| Profit Margin | `SUM([Profit]) / SUM([Sales])` | Measures profitability efficiency per category/region |
| Cost | `[Sales] - [Profit]` | Derives implied cost of goods sold |
| Avg Order Value | `SUM([Sales]) / COUNTD([Order ID])` | Tracks average transaction size by segment/region |
| Return Rate | `SUM([Return Flag]) / COUNT([Order ID])` | Monitors return risk across dimensions |
| Shipping Delay Bucket | `IF [Delivery Days] <= 1 THEN "Express (0-1d)" ELSEIF [Delivery Days] <= 3 THEN "Fast (2-3d)" ELSEIF [Delivery Days] <= 5 THEN "Standard (4-5d)" ELSE "Delayed (6+d)" END` | Categorizes delivery performance for pattern analysis |

---

## Insight 1: Technology Dominates Sales and Profit

**Observation:** Technology accounts for $153.9M (70.9%) of total sales and $28.0M (84.2%) of total profit.

**Data evidence:** Furniture: $51.6M sales, $3.6M profit (6.9% margin). Office Supplies: $11.5M sales, $1.7M profit (14.9%). Technology: $153.9M sales, $28.0M profit (18.2% margin).

**Business interpretation:** The company is heavily dependent on Technology for profitability. Technology's 18.2% margin exceeds both target and peer categories.

**Recommended action:** Protect Technology margin through pricing discipline. Avoid deep Technology discounts that could erode this category's outsized contribution. Simultaneously, develop plans to reduce concentration risk.

---

## Insight 2: Furniture Margin Is Structurally Below Target

**Observation:** Furniture's profit margin is 6.9% — less than half the company target of 15%.

**Data evidence:** Tables: 5.7% margin | Bookcases: 5.7% margin | Furnishings: 7.9% | Chairs: 8.2% — all below target. Furniture generates $3.6M profit on $51.6M sales.

**Business interpretation:** Furniture's margin gap costs the business approximately $4.2M annually in "lost" profit vs. a 15% target margin. Either pricing is too low, supplier costs are too high, or promotion levels are eroding realized revenue.

**Recommended action:** Conduct a Furniture pricing audit. Test 5–8% price increases on Tables and Bookcases in one region as a pilot. Negotiate cost reductions with Furniture suppliers.

---

## Insight 3: Discounting Beyond 20% Generates Net Losses

**Observation:** Average profit per order declines dramatically with discount depth. Orders with 31%+ discounts have a negative average profit of –$1,601.

**Data evidence:** No discount: avg profit $13,203 | 1–10%: $10,010 | 11–20%: $6,336 | 21–30%: $3,181 | 31%+: –$1,601. Total losses from 31%+ discount orders: –$102,494.

**Business interpretation:** There is no evidence that heavy discounting generates compensating volume. With 64 orders at 31%+ discounts generating a net loss, these promotions are directly destroying value.

**Recommended action:** Immediately cap discount authorizations at 20% without senior leadership approval. Review the 64 loss-making high-discount orders to identify whether they were strategic or erroneous.

---

## Insight 4: South Region Leads in Sales Volume

**Observation:** South generates the highest regional sales at $64.7M across 1,210 orders.

**Data evidence:** South: $64.7M, 15.4% margin | North: $54.6M, 15.2% | West: $48.9M, 15.1% | East: $48.9M, 15.6%.

**Business interpretation:** South is the volume leader. East has the best margin efficiency at 15.6%. All four regions are within 0.5 percentage points of each other on margin, suggesting operational consistency.

**Recommended action:** Study what drives South's volume leadership — store density, demographics, campaign mix — and apply learnings to East and West where headroom exists.

---

## Insight 5: Home Office Segment Has the Highest Return Rate

**Observation:** Home Office customers return orders at a rate of 6.0% vs 4.0% for Consumer and Corporate segments.

**Data evidence:** Home Office: 1,446 orders, 6% return rate | Consumer: 1,355 orders, 4% | Corporate: 1,399 orders, 4%.

**Business interpretation:** Home Office buyers are 50% more likely to return items. This may reflect product-fit mismatches (buying office equipment for home use), sizing issues (ordering bulk quantities then returning), or lower brand loyalty.

**Recommended action:** Investigate Home Office return reasons using order notes or customer surveys. Introduce better product descriptions and sizing guides for Home Office buyers, particularly for Furniture orders.

---

## Insight 6: Same Day Shipping Has the Lowest Return Rate (2.1%)

**Observation:** Same Day shipping achieves a 2.1% return rate — significantly lower than all other modes (5% for First Class, Second Class, and Standard Class).

**Data evidence:** Same Day: 0.4 avg days, 2.1% return rate, 241 orders | First Class: 1.77 days, 5.1% | Standard Class: 4.71 days, 5.0%.

**Business interpretation:** Fast delivery reduces returns. Customers who receive orders quickly are far less likely to cancel or reconsider. Same Day's 2.1% return rate vs 5.0% Standard Class could indicate that shipping speed prevents buyer's remorse.

**Recommended action:** Quantify the cost of Standard Class returns (reprocessing, shipping back, restocking) and compare to the cost premium of upgrading to Second Class or First Class. Test a nudge offering "upgrade to First Class for $X" at checkout.

---

## Insight 7: Copiers Is the Most Profitable Sub-Category

**Observation:** Copiers generates $7.3M in profit — the highest of any sub-category — with an 18.0% margin.

**Data evidence:** Copiers: $40.6M sales, $7.3M profit, 18.0% margin | Accessories: $39.2M, $7.2M, 18.3% | Phones: $38.4M, $7.1M, 18.5%. All three are Technology sub-categories.

**Business interpretation:** Copiers, Accessories, and Phones form a profit trifecta within Technology. Together they generate $21.6M in profit (64.9% of company total) from $118.2M in sales.

**Recommended action:** Prioritize shelf space, digital placement, and cross-sell opportunities for these three sub-categories. Ensure inventory availability rates are highest in these SKUs.

---

## Insight 8: Standard Class Shipping Carries the Highest Revenue Risk

**Observation:** 58% of orders (2,435) use Standard Class shipping, which has the longest average delivery time (4.71 days) and tied-highest return rate (5.0%).

**Data evidence:** Standard Class: 2,435 orders, $125.6M in sales, 4.71 avg delivery days, 5.0% return rate.

**Business interpretation:** Standard Class is the default mode for the majority of orders, but its slow delivery may be silently costing revenue through elevated return rates. At 5% return rate and $125.6M Standard Class sales, the implied returned value is approximately $6.3M in gross sales.

**Recommended action:** Model the full cost of Standard Class returns including reverse logistics, restocking, and lost lifetime value. Develop a tiered shipping strategy where high-value orders (>$10K) are automatically upgraded to First Class.

---

## Insight 9: Organic Channel Drives 40%+ of Sales Volume

**Observation:** The Organic channel accounts for the largest share of sales among all campaign channels.

**Data evidence:** Organic: 1,694 orders (~40.3%) | Paid: 849 (~20.2%) | Email: 657 (~15.6%) | Social: 584 (~13.9%) | Referral: 392 (~9.3%).

**Business interpretation:** Strong organic demand indicates brand health. Paid and Email are the most controllable levers for growth campaigns. Referral, while the smallest channel, typically signals the highest customer quality.

**Recommended action:** Develop a referral incentive program to grow the Referral channel. Audit Paid channel ROI against order-level profitability — if Paid orders have lower margins, the ROAS calculation needs adjustment.

---

## Insight 10: Furniture Return Rate Is the Highest at 7.7%

**Observation:** Furniture has a 7.7% return rate — more than double Technology's 3.0%.

**Data evidence:** Furniture: 7.7% | Office Supplies: 3.7% | Technology: 3.0%.

**Business interpretation:** High Furniture returns compound the category's already low margins. A 7.7% return rate on $51.6M in Furniture sales implies approximately $4.0M in gross returns, further reducing realized revenue.

**Recommended action:** Add quality verification steps for Furniture orders before dispatch. Provide better assembly instructions and size guides. Consider mandatory image-based product reviews to reduce expectation mismatch.
