# Aggregate Functions and Grouping in MySQL

## Objective
Learn how to use aggregate functions (`SUM`, `COUNT`, `AVG`) and grouping in MySQL to summarize and analyze tabular data effectively.

---

## Table Structure

We use a sample table called `sales` with the following columns:

| Column   | Type          | Description                 |
| -------- | ------------- | --------------------------- |
| id       | INT           | Primary key, auto-increment |
| product  | VARCHAR(50)   | Product name                |
| category | VARCHAR(50)   | Product category            |
| quantity | INT           | Quantity sold               |
| price    | DECIMAL(5, 2) | Price per unit              |

---

## Step-by-Step Instructions

### 1. Create the `sales` Table
```MySQL
create database salse;
create table sales (id INT AUTO_INCREMENT PRIMARY KEY, product VARCHAR(50), category VARCHAR(50), quantity INT, price DECIMAL(5, 2));
SELECT * FROM sales.sales;
use sales;
desc sales;
insert into sales (product, category, quantity, price) values ('Apple', 'Fruit', 10, 1.2);
insert into sales (product, category, quantity, price) values ('Mango', 'Fruit', 20, 5.4);
insert into sales (product, category, quantity, price) values ('Carrot', 'Vegetable', 15, 0.8);
select SUM(quantity) AS total_quantity, AVG(price) AS average_price, COUNT(*) AS total_sales from sales;
select category, SUM(quantity) AS total_quantity, AVG(price) AS average_price, COUNT(*) AS number_of_products from sales GROUP BY category;
select category, SUM(quantity) AS total_quantity from sales GROUP BY category HAVING total_quantity > 20;
select product, SUM(quantity) AS total_quantity, AVG(price) AS average_price from sales GROUP BY product;
select category, product, SUM(quantity) AS total_quantity from sales GROUP BY category, product;
