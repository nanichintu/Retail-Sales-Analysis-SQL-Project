# SQL Query Practice: Beginner to Master Level

This repository contains a collection of SQL query exercises designed to help you practice and master SQL using a sample `sales_data` table with the following columns:

### 📊 Table Structure: `sales_data`

```sql
customer_id INT,
sale_date DATE,
sale_time TIME,
gender VARCHAR(10),
age INT,
category VARCHAR(50),
quantity INT,
price_per_unit DECIMAL(10, 2),
total_sale DECIMAL(10, 2),
year INT,
month INT,
timeofday VARCHAR(20),
name_day VARCHAR(20)
```

---

## 🟢 Beginner Level

### 1. Get all records from the table

```sql
SELECT * FROM sales_data;
```

### 2. Show unique categories of products

```sql
SELECT DISTINCT category FROM sales_data;
```

### 3. Count total number of sales transactions

```sql
SELECT COUNT(*) AS total_transactions FROM sales_data;
```

### 4. Find total sale amount for each customer

```sql
SELECT customer_id, SUM(total_sale) AS total_spent
FROM sales_data
GROUP BY customer_id;
```

### 5. Show sales made in the month of January

```sql
SELECT * FROM sales_data
WHERE month = 1;
```

---

## 🟡 Intermediate Level

### 6. Calculate average price per unit for each category

```sql
SELECT category, AVG(price_per_unit) AS avg_price
FROM sales_data
GROUP BY category;
```

### 7. Find the highest sale transaction

```sql
SELECT * FROM sales_data
ORDER BY total_sale DESC
LIMIT 1;
```

### 8. Get number of products sold by gender

```sql
SELECT gender, SUM(quantity) AS total_quantity
FROM sales_data
GROUP BY gender;
```

### 9. List total sales per day

```sql
SELECT sale_date, SUM(total_sale) AS daily_sales
FROM sales_data
GROUP BY sale_date;
```

### 10. Find customers who made purchases in more than one month

```sql
SELECT customer_id, COUNT(DISTINCT month) AS months_active
FROM sales_data
GROUP BY customer_id
HAVING COUNT(DISTINCT month) > 1;
```

---

## 🔴 Advanced Level

### 11. Calculate total sales by time of day (morning, afternoon, evening)

```sql
SELECT timeofday, SUM(total_sale) AS total_sales
FROM sales_data
GROUP BY timeofday;
```

### 12. Find top 3 customers with highest total sales

```sql
SELECT customer_id, SUM(total_sale) AS total_spent
FROM sales_data
GROUP BY customer_id
ORDER BY total_spent DESC
LIMIT 3;
```

### 13. Monthly sales trend for each category

```sql
SELECT category, month, SUM(total_sale) AS monthly_sales
FROM sales_data
GROUP BY category, month
ORDER BY category, month;
```

### 14. Find the average age of customers buying each category

```sql
SELECT category, AVG(age) AS avg_age
FROM sales_data
GROUP BY category;
```

### 15. Get sales data only for weekends

```sql
SELECT * FROM sales_data
WHERE name_day IN ('Saturday', 'Sunday');
```

---

### ✅ Tools
* Postgres
* mysql

Feel free to contribute or fork the project!
