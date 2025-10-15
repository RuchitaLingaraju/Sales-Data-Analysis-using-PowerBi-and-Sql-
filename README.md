🧠 Sales Data Analysis Using SQL and Power BI

📊 Project Overview

This project focuses on analyzing sales performance data using SQL for data querying and Power BI for interactive visualization. The goal is to uncover valuable business insights such as revenue trends, market performance, and product distribution across different regions.
By combining SQL-based data extraction and Power BI’s visualization capabilities, this analysis helps business teams make data-driven decisions to improve profitability, market targeting, and sales efficiency.

🎯 Objectives

Retrieve and analyze sales, customer, and transaction data using SQL queries.
Identify high-performing markets, customers, and product categories.
Evaluate yearly and monthly revenue trends.
Build a Power BI dashboard to visualize KPIs like total revenue, market performance, and currency-based sales.

🗂️ Datasets Used

The project uses the following datasets stored in a relational database:
Customers Table – Contains customer details such as customer ID, name, and region.
Transactions Table – Stores sales transactions with details like order date, product code, market code, sales amount, and currency.
Date Table – Includes calendar information such as date, month, and year for time-based analysis.

🧩 SQL Analysis Queries

1️⃣ Show all customer records

SELECT * FROM customers;

2️⃣ Show total number of customers

SELECT COUNT(*) FROM customers;

3️⃣ Show transactions for Chennai market (market code for Chennai is Mark001)

SELECT * FROM transactions 
WHERE market_code = 'Mark001';

4️⃣ Show distinct product codes sold in Chennai

SELECT DISTINCT product_code 
FROM transactions 
WHERE market_code = 'Mark001';

5️⃣ Show transactions where currency is US dollars

SELECT * 
FROM transactions 
WHERE currency = 'USD';

6️⃣ Show transactions in 2020 (join with date table)

SELECT transactions.*, date.* 
FROM transactions 
INNER JOIN date 
  ON transactions.order_date = date.date 
WHERE date.year = 2020;

7️⃣ Show total revenue in year 2020

SELECT SUM(transactions.sales_amount) AS total_revenue 
FROM transactions 
INNER JOIN date 
  ON transactions.order_date = date.date 
WHERE date.year = 2020 
  AND (transactions.currency = 'INR' OR transactions.currency = 'USD');
  
8️⃣ Show total revenue in year 2020 (January)

SELECT SUM(transactions.sales_amount) AS january_revenue 
FROM transactions 
INNER JOIN date 
  ON transactions.order_date = date.date 
WHERE date.year = 2020 
  AND date.month_name = 'January' 
  AND (transactions.currency = 'INR' OR transactions.currency = 'USD');
  
9️⃣ Show total revenue in 2020 in Chennai

SELECT SUM(transactions.sales_amount) AS chennai_revenue 
FROM transactions 
INNER JOIN date 
  ON transactions.order_date = date.date 
WHERE date.year = 2020 
  AND transactions.market_code = 'Mark001';
  
📈 Power BI Dashboard

The Power BI dashboard was created to visualize the key findings from SQL analysis.

Key Visuals Include:

💰 Total Revenue by Year & Month – Tracks revenue trends over time.
🌍 Market-Wise Sales Distribution – Highlights top-performing regions.
🛒 Product Performance Analysis – Displays sales by product categories.
💱 Currency Comparison – Compares total sales in INR vs USD.
🧍‍♂️ Customer Overview – Shows number of customers and their contributions to total revenue.

⚙️ Tools & Technologies

SQL (MySQL / PostgreSQL) – for data extraction and analysis
Power BI – for creating dashboards and visual storytelling
Excel / CSV – for initial data formatting
GitHub – for version control and portfolio sharing

🚀 Key Insights

Chennai market showed significant sales contribution in 2020.
January 2020 marked a noticeable revenue peak.
The business operated in both INR and USD, indicating multi-country sales.
Distinct product codes in Chennai revealed diversified sales strategy.

🧑‍💻 Author
👤 Ruchita Lingaraju
📍 Northeastern University – Data Analytics Engineering
💼 Passionate about Data Analytics, Business Intelligence, and Data-Driven Decision Making.
