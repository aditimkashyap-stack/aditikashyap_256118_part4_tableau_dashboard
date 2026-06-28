# Executive Dashboard Story
## Retail Chain Sales Performance | Jan 2024 – Dec 2025

---

## Executive Summary

Across 4,200 orders spanning January 2024 to December 2025, the retail chain generated **$217 million in total sales** with a **$33.3 million profit** and an overall profit margin of **15.3%** — fractionally above the 15% internal target. At a headline level, the business is healthy and growing. However, the dashboard reveals three structural risks that leadership must act on: **Furniture's chronic margin underperformance (6.9%)**, **Home Office segment's elevated return rate (6%)**, and a clear pattern showing that **discounts above 20% erode profit to near zero**.

---

## What Is Performing Well

**Technology is carrying the business.** At $153.9M in sales and an 18.2% profit margin, Technology represents 71% of total sales and 84% of total profit. Sub-categories like Copiers ($7.3M profit), Accessories ($7.2M), and Phones ($7.1M) are consistently high-margin. The business's strongest economic engine is functioning well.

**The South and West regions are outperformers.** South generates the highest absolute sales ($64.7M) and West shows the best margin efficiency relative to order count. Both regions sustain margins around the company average.

**Same Day shipping delights customers.** With an average delivery time of 0.4 days and a 2.1% return rate, Same Day is by far the highest-performing shipping mode in both speed and customer satisfaction. It is, however, used only 5.7% of the time (241 orders).

**Campaign contribution is diverse.** Organic accounts for 40.3% of sales volume, showing healthy brand pull without purely paid acquisition dependence. Paid and Email campaigns contribute meaningfully (20.2% and 15.6%).

---

## What Is Underperforming

**Furniture is structurally unprofitable relative to peers.** At a 6.9% profit margin, Furniture generates $51.6M in sales but only $3.6M in profit. Within Furniture, Tables (5.7% margin) and Bookcases (5.7% margin) are the weakest performers. Pricing, supplier costs, or promotional strategies in this category need urgent review.

**Standard Class shipping dominates but disappoints.** With 2,435 of 4,200 orders (58%) shipped Standard Class, average delivery takes 4.71 days — the slowest mode — and carries a 5% return rate. There is no cost-saving reason for Standard Class shipping to dominate if it is correlated with returns.

**Discounting beyond 20% destroys profit.** Average profit falls from $13,203 (no discount) to $3,181 (21–30% discount) and turns negative at 31%+ discounts (–$1,601 average). Orders with 31%+ discounts generate $102,494 in total losses. Discounting appears to have no volume-compensating effect.

---

## What Risks Are Visible

1. **Furniture margin compression**: If Furniture's margin drops below 5%, it becomes a net value drain on capital and floor space.
2. **Home Office return concentration**: At 6% return rate (vs 4% Consumer/Corporate), Home Office customers are nearly 50% more likely to return orders. The pattern likely reflects B2B buyers buying for resale or home use mismatch.
3. **Revenue concentration in Technology**: 71% of sales in one category creates significant concentration risk. Any supply chain disruption, competitor price war, or demand shift in Technology would have an outsized P&L impact.
4. **Delayed shipments in Standard Class**: If Standard Class returns (5%) drive secondary fulfillment costs, the effective margin on these orders may be materially worse than stated.

---

## What Opportunities Are Visible

1. **Upsell Standard Class to Second Class or First Class shipping**: Second Class averages 2.68 days at a 5% return rate — similar return risk but 2 fewer days delivery time. First Class at 1.77 days achieves the same 5% return with meaningfully faster delivery. Offering First Class at a small premium could improve customer NPS and reduce return-related costs.
2. **Reprice or phase out deep-discount promotions**: Removing campaigns that trigger 31%+ discounts would eliminate the loss-generating tail with no apparent volume benefit.
3. **Invest in Technology expansion in the East region**: East has the lowest Technology share of sales by region (based on category mix), representing a headroom opportunity.
4. **Furniture sub-category rationalization**: Exiting Bookcases (5.7% margin) or renegotiating supplier contracts for Tables could lift overall Furniture margin toward 9–10% within 2 quarters.

---

## Recommended Business Actions

| Priority | Action | Expected Impact |
|---|---|---|
| High | Cap promotional discount tiers at 20% maximum | Eliminate $102K+ in discount-driven losses |
| High | Review Furniture pricing strategy (Tables, Bookcases) | Recover 200–300bps of margin in this category |
| Medium | Investigate Home Office return drivers (product fit, sizing, delivery) | Reduce segment return rate from 6% to 4% |
| Medium | Shift 15% of Standard Class volume to First/Second Class | Improve NPS; potentially reduce returns |
| Low | Expand Technology promotion in East region | Drive incremental revenue in lower-penetration market |

---

## Limitations of the Dashboard

- **No customer-level LTV analysis.** Return rates are measured per order, not per customer lifetime. A single customer making 3 returns distorts segment-level analysis.
- **No cost structure breakdown.** Profit = Sales – Costs, but the dashboard cannot decompose costs into COGS, marketing, shipping, and overhead. Furniture's low margin could reflect high COGS or high freight cost — both require different interventions.
- **32 missing customer_rating values and 24 missing campaign_channel values.** These gaps are small but could bias segment-level campaign performance analysis.
- **Only 2 years of data.** Seasonality is visible but not validated. December peaks may be structural or year-specific.
- **Geographic granularity is state/city level** but the dashboard aggregates to region for most views. Store-level variation within regions is not visible.

---

## Suggested Next Analysis

1. **Cohort retention analysis**: Identify whether returning customers (non-return customers) generate higher LTV to justify the cost of quality programs.
2. **Shipping cost model**: Build a cost-benefit model comparing shipping modes including returned-order reprocessing costs.
3. **Furniture category deep-dive**: Supplier-level profitability analysis to identify whether margin losses are driven by specific vendors.
4. **Discount effectiveness A/B test**: Run a controlled experiment testing whether orders without discounts generate comparable units sold — current data is observational and subject to selection bias.
