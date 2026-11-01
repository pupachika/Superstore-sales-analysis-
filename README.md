# Superstore sales analysis: where the profit comes from, and where it leaks

An end-to-end analysis of a US retailer's sales (2015-2018) in Python: data cleaning, KPIs, seasonality, profitability, the cost of discounts, customer segmentation (RFM) and a back-tested sales forecast, finished with five business recommendations.

**[Open the full report (HTML)](superstore_analysis.html)** | [Notebook](superstore_analysis.ipynb)

![Dashboard](charts/00_dashboard.png)

> **About the data.** *Sample - Superstore* is a well-known **demonstration dataset** of a fictional US retailer (9,994 order lines, 2015-2018). The findings show the method, not facts about a real company. Source: [leonism/sample-superstore](https://github.com/leonism/sample-superstore). The notebook downloads it automatically.

## Business question

Sales grew about 15% a year. Is the growth healthy, which parts of the business make or lose money, and what should management do in 2019?

## Key findings

| Finding | Number |
|---|---|
| Total sales / profit / margin | $2.30M / $286k / 12.5% |
| Sales growth 2015 to 2018 | $484k to $733k (about +15% a year) |
| Growth driver | Orders per customer 1.6 to 2.4; customers only +16% |
| Margin trend | 13.4% (2017) down to 12.7% (2018) |
| Seasonality | Sep-Dec produce about 50-54% of annual sales; Feb is 0.30x an average month |
| Profit concentration | Technology and Office Supplies give 94% of profit; Furniture 32% of sales but 6% of profit |
| Loss-making products | Tables (-$17.7k), Bookcases (-$3.5k), Supplies (-$1.2k) |
| **Discounts above 20%** | 14% of lines, 16% of sales, **lose $135k = 47% of the profit earned elsewhere** |
| Loss-making states | 10 of 49, total -$98k (Texas, Ohio, Pennsylvania, Illinois worst) |
| Customers | Top 20% of customers = 48% of sales; "At risk" segment holds $477k of sales |
| 2019 forecast | About $910k (+24%); back-test 2018 MAPE 18.5% vs 24.5% for the naive baseline; wide uncertainty |

## Recommendations (details in the notebook)

1. Cap discounts at 20% with an approval step above it. Test it in one region first.
2. Reprice or rethink Tables, Bookcases and Supplies.
3. Review discount policy in Central and in the loss-making states.
4. Run a win-back campaign for the 136 "At risk" customers.
5. Plan stock, staff and ads around Sep-Dec; avoid deep discounts in Jan-Feb.

## Methods and skills shown

- **Data cleaning and validation:** removing 806 empty rows, type conversion, business-rule assertions, a cleaning log.
- **Exploratory and business analysis:** KPIs by year, seasonality index, sub-category and state profitability, discount-band analysis.
- **Customer analytics:** RFM scoring and segmentation, Pareto concentration.
- **Forecasting:** Holt-Winters with a hold-out back-test against a naive baseline, scenario table and simulation range.
- **Communication:** consistent chart design, a one-page dashboard, findings written for non-technical readers, explicit limitations.

## Limitations

- Demonstration dataset of a fictional retailer.
- Only four years of data; the forecast is validated on one hold-out year.
- Discounts and margin are correlated; the causal effect needs an experiment.
- Profit is taken as given (no cost, marketing or returns breakdown).

## Run it yourself

```bash
pip install -r requirements.txt
jupyter notebook superstore_analysis.ipynb
```

The notebook creates `data/` and `charts/` on its own.

## Author

Bogdan, Belgrade, Serbia. Interested in data analysis, e-commerce and marketing analytics.
[LinkedIn](https://www.linkedin.com/in/your-profile) | [GitHub](https://github.com/your-username)
