# Olist E-commerce Data Pipeline (Python + MySQL)

## Overview
End-to-end data project on the Olist Brazilian e-commerce dataset.
Raw CSV files are cleaned in Python (pandas), combined into an
analysis-ready orders table, and loaded into MySQL.

## Tech Stack
Python (pandas, SQLAlchemy), MySQL, MySQL Workbench, Jupyter Notebook

## Dataset
 Olist Brazilian e-commerce dataset (Kaggle): orders, customers,
order items, payments, products, sellers, category translation.

## Pipeline Steps
1. **Cleaning:** converted timestamp columns to datetime, filled
   missing product categories, translated category names to English.
2. **Aggregation:** summarized order items and payments to one row
   per order before joining (avoids duplicate rows and double-counted revenue).
3. **Feature engineering:** created total_revenue, freight_ratio,
   avg_item_price, delivery_delay_days and order_month.
4. **Loading:** wrote the orders, customers, products and sellers
   tables to MySQL using `DataFrame.to_sql()`.

## Validation
- 99,441 orders in the source data and 99,441 rows in the final table
- `order_id` is unique, so there are no duplicate rows after joins
- Total item revenue matches the raw order_items data

## Project Files
- `OList_PipeLine.ipynb`: complete pipeline notebook

## How to Run
1. Download the Olist Brazilian e-commerce dataset from Kaggle
2. Update the CSV paths in the notebook to match your folder
3. Update the MySQL username and password in the connection string
4. Run the notebook cells in order
