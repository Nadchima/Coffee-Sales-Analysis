# Coffee Sales Analysis

An exploratory analysis of coffee-shop transactions that examines product demand, revenue patterns, peak hours, weekday performance, and monthly trends.

## Project objective

The project demonstrates data preparation, exploratory data analysis, aggregation, and visualization with Python. It answers the following questions:

- Which coffee has the highest number of transactions?
- Which coffee generates the most revenue?
- At what hour is revenue highest?
- Which weekday and month perform best?
- How is revenue distributed across morning, afternoon, and night?

## Tools and data

- Python
- pandas, NumPy, Matplotlib, and Seaborn
- Google Colab/Jupyter Notebook
- [Coffee Sales Dataset by Navjot Kaushal on Kaggle](https://www.kaggle.com/datasets/navjotkaushal/coffee-sales-dataset)

The included CSV contains 3,547 transactions recorded from 1 March 2024 through 23 March 2025. It has 11 fields covering transaction value, coffee name, payment type, date, time, hour, weekday, month, and time of day.

| Data-quality check | Result |
|---|---:|
| Rows | 3,547 |
| Columns | 11 |
| Missing values | 0 |
| Duplicate rows | 0 |
| Payment method | Card for all records |

## Analysis workflow

1. Load and inspect the transaction data.
2. Validate missing values, duplicates, and data types.
3. Aggregate transaction count and revenue by coffee type.
4. Summarize revenue by hour, weekday, month, and time of day.
5. Visualize the main product and time-based patterns.

## Results

| Metric | Result |
|---|---:|
| Total transaction value | 112,245.58 |
| Number of transactions | 3,547 |
| Average value per active day | 294.61 |
| Top coffee by transaction count | Americano with Milk — 809 |
| Top coffee by revenue | Latte — 26,875.30 |
| Highest-revenue hour | 10:00 — 10,198.52 |
| Highest-revenue weekday | Tuesday — 18,168.38 |
| Highest-revenue month | March — 15,891.64 |
| Highest-revenue time period | Night — 38,186.34 |

The `money` field is treated as transaction value. The source files do not establish that it is denominated in US dollars, so the results are intentionally reported without a currency symbol.

## Key findings

- **Americano with Milk leads by volume**, with 809 transactions. This is the correct product to describe as the most frequently purchased coffee.
- **Latte leads by revenue**, generating 26,875.30. High revenue does not mean it has the highest transaction count.
- **10:00 is the strongest hour by revenue**, producing 10,198.52 across the observation period.
- **Tuesday has the highest aggregated weekday revenue**, while March has the highest aggregated monthly revenue.
- **Night records the highest time-of-day revenue**, but it is only slightly above Afternoon: 38,186.34 versus 38,130.04. This difference should not be treated as a large performance gap.

These are descriptive findings from the available transactions. They do not by themselves establish seasonality or causality because the dataset covers an uneven portion of two calendar years and does not include store traffic, inventory availability, promotions, or product cost.

## Visualizations

### Transactions by coffee type

Americano with Milk has the highest transaction count.

<img width="992" height="590" alt="Transaction count by coffee type" src="https://github.com/user-attachments/assets/2e7cfc6b-8840-4f6e-8859-d0cfa05b540b" />

### Revenue by month

March has the highest aggregated revenue in the available data.

<img width="989" height="490" alt="Revenue by month" src="https://github.com/user-attachments/assets/dfc43644-9ab6-4c6c-837e-7d2ee1474356" />

### Revenue by hour

10:00 has the highest aggregated hourly revenue.

<img width="989" height="590" alt="Revenue by hour" src="https://github.com/user-attachments/assets/af809663-adda-4414-9d3d-87c319e0c934" />

## Repository contents

```text
.
├── Coffee_Sales_Analysis.ipynb
├── Coffe_sales.csv
└── README.md
```

## Run locally

```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook Coffee_Sales_Analysis.ipynb
```

Place `Coffe_sales.csv` in the same directory as the notebook. The data-loading cell checks the repository directory first and then the Kaggle input directory.

## Limitations and next steps

- Confirm the currency and data-collection context with the original data owner before attaching a currency symbol to `money`.
- Compare like-for-like months across complete years before making seasonal claims.
- Add product cost to calculate gross profit rather than revenue alone.
- Add transaction identifiers and store or machine identifiers if multiple sales locations are involved.
- Confirm dataset redistribution rights before publishing the CSV.
