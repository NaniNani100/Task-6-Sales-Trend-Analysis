# Task 6 – Sales Trend Analysis

This task analyzes monthly revenue and order volume using SQL.
I used an online SQL editor with SQLite. The final query uses 
strftime() to extract year and month, SUM() to calculate revenue,
and COUNT() for total orders.



## 📌 Objective
Analyze monthly **revenue** and **order volume** using aggregation functions in SQL.

---

## 🛠️ Tools Used
- Online SQL Editor (SQLite-based)
- SQL functions: `SUM()`, `COUNT()`, `strftime()`, `GROUP BY`, `ORDER BY`

---

## 📂 Dataset
Table used: **online_sales**

Columns:
- `order_id`
- `order_date`
- `amount`
- `product_id`

---

## 🧠 Approach
1. Extracted **year** and **month** using `strftime('%Y', order_date)` and `strftime('%m', order_date)`.
2. Grouped the data by **year** and **month**.
3. Calculated:
   - Total Revenue → `SUM(amount)`
   - Total Orders → `COUNT(DISTINCT order_id)`
4. Sorted results by year and month.
5. Exported outputs for GitHub submission.

---

## 🧾 Final SQL Query
```sql
SELECT 
    strftime('%Y', order_date) AS order_year,
    strftime('%m', order_date) AS order_month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_orders
FROM online_sales
GROUP BY 
    strftime('%Y', order_date),
    strftime('%m', order_date)
ORDER BY 
    order_year,
    order_month;
```

---

## 📈 Output Table

| order_year | order_month | total_revenue | total_orders |
|-----------|-------------|----------------|--------------|
| 2023 | 11 | 700 | 1 |
| 2023 | 12 | 1400 | 1 |
| 2024 | 01 | 2000 | 2 |
| 2024 | 02 | 2000 | 2 |
| 2024 | 03 | 2900 | 2 |


## ✔ Conclusion
This task helped analyze how sales change month-to-month using SQL aggregation and date extraction functions. It demonstrates useful techniques for trend analysis and business reporting.

