# Customer Behavior Analysis 🛍️

An end-to-end data analytics project: cleaning raw customer purchase data with **Python**, loading it into **PostgreSQL**, answering 10 business questions with **SQL**, and visualizing the results in an interactive **Power BI** dashboard.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)

---

## 📌 Project Pipeline

```
Raw CSV  →  Python (pandas) cleaning & feature engineering  →  PostgreSQL
         →  SQL analysis (10 business questions)  →  Power BI dashboard
```

This project mirrors a real analyst workflow: start with messy raw data, clean and shape it programmatically, move it into a proper database, use SQL to answer specific business questions, then visualize the findings for a non-technical audience.

---

## 🧹 Part 1 — Data Cleaning & Pipeline (Python)

**File:** [`data_cleaning_pipeline.ipynb`](data_cleaning_pipeline.ipynb)

- Loaded a raw customer shopping behavior dataset with pandas
- Filled missing `review_rating` values using the **median rating within each product category**, rather than a single global median
- Standardized column names (lowercase, underscores, cleaned up a messy `purchase_amount_(usd)` column name)
- Engineered an `age_group` feature by bucketing customers into quartiles (Young Adult / Adult / Middle Aged / Senior)
- Converted the categorical `frequency_of_purchases` field into a numeric `purchase_frequency_days` field for easier aggregation
- Identified and dropped a fully redundant column (`promo_code_used` was identical to `discount_applied` in every row)
- Loaded the cleaned dataset into PostgreSQL via SQLAlchemy, and exported a cleaned CSV copy

---

## 🗄️ Part 2 — SQL Analysis

**File:** [`customer_behavior_analysis.sql`](customer_behavior_analysis.sql)

10 business questions answered with SQL, covering revenue analysis, discount behavior, customer segmentation, and product performance:

1. Total revenue by gender
2. Customers who used a discount but still spent above average
3. Top 5 products by average review rating
4. Average purchase amount: Standard vs. Express shipping
5. Do subscribed customers spend more? (avg spend + total revenue)
6. Top 5 products by discount usage rate
7. Customer segmentation — New / Returning / Loyal (by purchase history)
8. Top 3 most purchased products, within each category
9. Do repeat buyers (5+ previous purchases) subscribe more often?
10. Revenue contribution by age group

**SQL concepts used:** aggregate functions, subqueries, `CASE` statements, `CTE`s (`WITH`), window functions (`ROW_NUMBER() OVER PARTITION BY`), conditional percentage calculations

---

## 📊 Part 3 — Power BI Dashboard

**File:** [`Customer_Behavior_Analysis.pbix`](Customer_Behavior_Analysis.pbix)

An interactive single-page dashboard built on the cleaned dataset, featuring:

- KPI cards (Number of Customers, Average Purchase Amount, Average Review Rating) — built with custom DAX measures
- Donut chart — subscription status breakdown
- Column & bar charts — spend and customer count by category and age group
- 4 interactive slicers — Subscription Status, Gender, Category, Shipping Type


---


## 📁 Repository Contents

```
├── data_cleaning_pipeline.ipynb        # Python: cleaning, feature engineering, load to PostgreSQL
├── customer_behavior_analysis.sql      # SQL: 10 business questions
├── Customer_Behavior_Analysis.pbix    # Power BI dashboard
└── README.md
```

---

## 🔗 Connect

- LinkedIn: https://www.linkedin.com/in/vikas-bhutadiya-643392245/
