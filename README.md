# E-Commerce SQL Data Analysis

Exploratory analysis of a Brazilian e-commerce dataset using **MySQL** and **Python** (pandas, matplotlib, seaborn). Raw data was loaded into a MySQL database, queried with SQL, and visualized in a Jupyter Notebook.

## Dataset

7 relational tables, ~100K orders:

* **customers** — 99,441 rows (customer_id, city, state, zip)
* **orders** — order status, purchase/delivery timestamps
* **order_items** — order_id, product_id, seller_id, price, freight_value
* **payments** — payment_type, installments, payment_value
* **products** — category, weight, dimensions
* **sellers** — seller_id, city, state
* **geolocation** — zip-code level lat/long mapping

## Tech Stack

* **MySQL** — data storage & querying
* **Python** — `pandas`, `numpy`, `matplotlib`, `seaborn`, `mysql.connector`
* **Jupyter Notebook** — analysis environment

## Key Insights

* **90,202** orders were placed in 2017
* **99.99%** of orders were paid in installments
* **Bed, Table & Bath** is the top revenue category — ₹1.37 crore (13.7M), contributing **42.79%** of its segment's revenue share
* **Furniture & Decoration** generated ₹1.14 crore (11.4M) in sales
* Correlation between product price and purchase frequency: **-0.106** (weak negative — cheaper products sell slightly more often)
* **2017 vs 2016** year-over-year sales growth: **+12,112%** (low 2016 base)
* **2018 vs 2017** year-over-year sales growth: **+20%**
* Top customer city by average products/order: **Padre Carvalho** (28 items/order)

## Analysis Performed

1. Unique customer cities
2. Total orders placed in 2017
3. Total sales by product category
4. % of orders paid in installments
5. Customer distribution by state (bar chart)
6. Monthly order volume in 2018 (bar chart)
7. Average products per order, by customer city
8. Revenue contribution % by category
9. Correlation: price vs. purchase frequency
10. Seller revenue ranking (`DENSE_RANK()`)
11. Moving average of order value per customer (window function)
12. Cumulative monthly sales by year
13. Year-over-year sales growth rate (`LAG()`)
14. 6-month customer retention rate
15. Top 3 highest-spending customers per year

## SQL Concepts Used

* Joins across 4-5 tables
* `GROUP BY` aggregations
* Window functions: `DENSE_RANK()`, `LAG()`, moving `AVG() OVER()`
* CTEs (`WITH` clauses)
* Subqueries for percentage calculations
* Date functions: `YEAR()`, `MONTH()`, `MONTHNAME()`, `DATE_ADD()`

## File Structure

```
├── py_sql.ipynb          # Main notebook (SQL queries + Python visualization)
├── customers.xlsx
├── orders.xlsx
├── order_items.xlsx
├── payments.xlsx
├── products.xlsx
├── sellers.xlsx
├── geolocation.xlsx
└── README.md
```

## How to Run

1. Import the Excel files into a MySQL database named `ecommerce`
2. Update DB credentials in the first notebook cell
3. Run all cells in `py_sql.ipynb`

## Requirements

```
pandas
numpy
matplotlib
seaborn
mysql-connector-python
```
