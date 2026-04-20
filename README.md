# sales-trend-analysis-sql
# Sales Trend Analysis Using SQL (SQLite)

# Project Overview

This project analyzes monthly sales performance using SQL aggregation techniques in SQLite.  
The goal is to identify revenue trends and order volume over time using transactional sales data.

- SQL Aggregations
- GROUP BY
- ORDER BY
- Date Functions
- Business Trend Analysis

# Objective
  Analyze:
- Monthly Revenue
- Monthly Order Volume
  Using SQL queries on an `online_sales` dataset.

# Tools Used

- SQLite
- DB Browser for SQLite

# Dataset:
Table Name: `online_sales`

| Column Name | Data Type |
|------------|-----------|
| order_id | INTEGER |
| order_date | TEXT |
| amount | REAL |
| product_id | INTEGER |

# Output Screenshot: <img width="1920" height="1020" alt="Image" src="https://github.com/user-attachments/assets/578e74d5-4fae-4d1a-bc2b-ccf0a40d0b65" />


# SQL Query Used

```sql
SELECT 
strftime('%Y-%m', order_date) AS month,
SUM(amount) AS total_revenue,
COUNT(order_id) AS total_orders
FROM online_sales
GROUP BY month
ORDER BY month;

