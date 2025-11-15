📚 Online Bookstore Management System (SQL Project)

This project is a complete SQL-based Database Management & Data Analysis System created for an Online Bookstore.
It demonstrates hands-on skills in Database Design, SQL Querying, Joins, Aggregations, and Business Insights, which are essential for Data Analyst and SQL Developer roles.

🚀 Project Overview

This project simulates a real Online Bookstore environment where SQL is used to:

Manage book inventory

Store customer details

Track orders & sales

Analyze revenue and purchasing behavior

Generate business insights using SQL queries

The repository includes the full SQL script and a formatted PDF report.

🛠️ Tech Stack Used

PostgreSQL

SQL (DDL, DML, Joins, CTEs, Aggregations)

Basic Data Analysis concepts

📁 Files in This Repository
📦 Online Bookstore Management System
 ┣ 📄 Online_Book_Store_Management_System.sql   → Complete SQL Code
 ┗ 📄 Online_Book_Store_Management_System.pdf   → Project Documentation


Note:
The CSV datasets used for import are not included.
However, the SQL queries and structure can be executed with any similar dataset.

🏗️ Database Structure
1. Books Table

Book_ID

Title

Author

Genre

Published_Year

Price

Stock

2. Customers Table

Customer_ID

Name

Email

Phone

City

Country

3. Orders Table

Order_ID

Customer_ID

Book_ID

Order_Date

Quantity

Total_Amount

These tables are connected via primary key–foreign key relationships to perform multi-table analysis.

📊 Key Features & Insights
✔ Inventory Management

Total stock calculation

Lowest stock books

Most expensive books

Genre-wise availability

✔ Customer Analysis

Customers placing multiple orders

Highest spending customer

City-wise customer spending

✔ Sales & Revenue

Total revenue generated

Orders above specific thresholds

Most frequently ordered books

Quantity sold by genre & author

🔍 Sample SQL Queries
🔹 Total Revenue
SELECT SUM(total_amount) AS Revenue FROM Orders;

🔹 Books Sold by Genre
SELECT b.genre, SUM(o.quantity) AS total_books_sold
FROM Orders o
JOIN Books b ON o.book_id = b.book_id
GROUP BY b.genre;

🔹 Most Frequently Ordered Book
SELECT o.book_id, b.title, COUNT(o.order_id) AS order_count
FROM orders o
JOIN books b ON o.book_id = b.book_id
GROUP BY o.book_id, b.title
ORDER BY order_count DESC
LIMIT 1;

🔹 Stock Remaining After Orders
SELECT b.book_id, b.title, b.stock,
       COALESCE(SUM(o.quantity),0) AS order_quantity,
       b.stock - COALESCE(SUM(o.quantity),0) AS remaining_quantity
FROM books b
LEFT JOIN orders o ON b.book_id = o.book_id
GROUP BY b.book_id
ORDER BY b.book_id;

📈 Skills Demonstrated

SQL Database Creation

Table Design (DDL)

Data Import Commands

Joins (INNER, LEFT)

Grouping & Aggregation

Analytical Problem Solving

Writing Clean SQL Queries

Business Insights & Reporting

📝 Conclusion

This project highlights practical SQL skills similar to real-world data analytics tasks such as:

Sales analysis

Customer insights

Inventory monitoring

Revenue calculation

It is an excellent demonstration of SQL knowledge for Data Analyst, Business Analyst, and SQL Developer roles.

⭐ If you found this project useful, feel free to star the repository!
