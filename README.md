# 🗄️ SQL for Data Analysis

Learn SQL the practical way: build a small shop database from scratch, then answer real business questions with queries.

## What you'll learn

- `SELECT`, `WHERE`, `ORDER BY`, `LIMIT` — pick, filter, sort rows
- Aggregations `COUNT` / `SUM` / `AVG` with `GROUP BY` and `HAVING`
- `INNER JOIN` — combine tables using a shared key
- `LEFT JOIN` — find rows with **no** match (e.g. customers who never ordered)
- Subqueries — a query inside another query
- Window function `RANK()` — rank rows without collapsing them

## Dataset

The notebook **creates** the database itself (`data/shop.db` using Python's built-in `sqlite3`):

| Table | Rows | Columns |
|---|---|---|
| customers | 1,000 | CustomerID, Name, City, JoinDate |
| products | 20 | ProductID, ProductName, Category, Price |
| orders | 10,000 | OrderID, CustomerID, ProductID, Quantity, OrderDate |

No download needed — run the notebook and the data is generated (seed 42, same data every run).

## How to run

```bash
pip install -r requirements.txt
jupyter notebook sql_analysis.ipynb
```

> `sqlite3` is part of Python's standard library — no install needed. Only `pandas` is required (to display query results nicely).

## Key findings

- **Total revenue:** Rs. 735,993,400
- **Top customer:** Rabia Ali — Rs. 3,026,400 spent
- **Monthly trend:** revenue peaked in January (Rs. 134.1M), dipped in February (Rs. 109.7M)
- **Best category:** Electronics — Rs. 584,318,000 revenue
- **200 customers** never placed an order (found with `LEFT JOIN`)

## 🎓 Explain it yourself

1. What is the difference between `WHERE` and `HAVING`?
2. When would you use a `LEFT JOIN` instead of an `INNER JOIN`?
3. What does `GROUP BY` do, and why do we need it with `COUNT(*)`?
4. Explain the subquery in Concept 5 in your own words — what runs first?
5. How would you change the monthly trend query to show revenue **per category per month**?
