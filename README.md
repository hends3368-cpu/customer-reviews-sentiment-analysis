# Customer Reviews Sentiment Analysis

A data analysis project that scores customer reviews with sentiment analysis in Python and visualizes the results in Power BI.

## What it does

1. Reads customer reviews from a SQL Server database (`PortfolioProject_MarketingAnalytics`, table `dbo.customer_reviews`).
2. Scores each review text with **NLTK VADER** to get a compound sentiment score from -1 (very negative) to +1 (very positive).
3. Exports the enriched table to `fact_customer_reviews_with_sentiment.csv`.
4. The CSV is loaded into a Power BI report for analysis.

## Dataset

`fact_customer_reviews_with_sentiment.csv` has 1,363 reviews dated from January 2023 to December 2025.

| Column | Description |
|---|---|
| ReviewID | Review identifier |
| CustomerID | Customer identifier |
| ProductID | Product identifier |
| ReviewDate | Date of the review |
| Rating | Star rating (1 to 5) |
| ReviewText | Review text |
| SentimentScore | VADER compound score (-1 to +1) |

Rating distribution: 5 stars: 409, 4 stars: 431, 3 stars: 290, 2 stars: 153, 1 star: 80. Average sentiment score: 0.19.

## Files

| File | Description |
|---|---|
| `customer_reviews_enrichment.py` | Python script: SQL Server extraction and sentiment scoring |
| `fact_customer_reviews_with_sentiment.csv` | Output table with sentiment scores |
| `marketing_analytics_dashboard.pbix` | Power BI report (open with Power BI Desktop) |

## Tools

- Python (pandas, NLTK VADER, pyodbc)
- SQL Server
- Power BI

## How to run

```bash
pip install pandas nltk pyodbc
python customer_reviews_enrichment.py
```

The script connects to a local SQL Server instance with Windows authentication. Update the `Server` value in `fetch_data_from_sql()` to match your own server.
