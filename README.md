# revenue-at-risk
# Revenue at Risk: Customer Win-Back Analysis

A mock Adobe Solution Consulting engagement. It finds the high-value customers a UK online retailer is losing, puts a £ figure on them, and designs an AI-agent win-back plan on Adobe Experience Cloud.

**Pitch deck:** [pitch-deck.pdf](pitch-deck.pdf)

## Key findings

- **77%** of revenue comes from the top 20% of customers
- **153** of those top customers have gone quiet (no order in 90 to 365 days)
- **£860,574 a year** of revenue at risk (about £5,600 per customer)
- Only **21%** of new customers reorder the following month
- Modelled base case: **£77,452 a year** net gain (10% win-back, minus a 10% discount)

![Yearly value by customer segment](chart1_value_by_segment.png)

![Monthly cohort retention](chart2_cohort_retention.png)

## Method

1. **Clean:** removed cancellations, guest checkouts and zero-price rows.
2. **Segment:** grouped customers by lifetime spend (top 20% = high value) and days since last order (90+ = going quiet, 365+ = lost).
3. **Value:** yearly value = each customer's past spend averaged per year.
4. **Retention:** grouped customers by first-order month and tracked what share ordered again in each later month.
5. **Business case:** recovered revenue at 5%, 10% and 15% win-back rates, minus a 10% discount.

## The Adobe solution

| Step | Adobe product | AI agent | What it does |
|---|---|---|---|
| 1. Unify data | Real-Time CDP | | One profile per customer |
| 2. Find the segment | Real-Time CDP | Audience Agent | Builds the at-risk segment from a plain-English prompt |
| 3. Build the journey | Journey Optimizer | Journey Agent | Designs the win-back email sequence |
| 4. Personalise content | GenStudio / Firefly | | Features each customer's favourite product |
| 5. Test the offer | Journey Optimizer Experimentation Accelerator | Experimentation Agent | Discount vs no discount, with a holdout group |
| 6. Prove the value | Customer Journey Analytics | Data Insights Agent | Recovered revenue vs the holdout |

A holdout group gets nothing, so the difference in spend proves the real uplift.

## Limits

- Win-back rate and discount cost are assumptions, not results.
- The data covers one retailer from 2009 to 2011, so this is a method demo.
- Yearly value describes past spend. It doesn't predict future spend.

## How to run

Open `Adobe_Revenue_at_Risk.ipynb` in Google Colab and choose Runtime → Run all. It downloads the dataset automatically.

**Data source:** UCI Machine Learning Repository, "Online Retail II".

*Independent personal project. Not affiliated with or endorsed by Adobe.*
