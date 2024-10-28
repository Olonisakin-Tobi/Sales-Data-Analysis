# Sales-Data-Analysis
						       -- Question 1:Database Creation & Schema Design
-- Create a database called `sales_data`
CREATE DATABASE sales_data;

-- products: `product_id` (INT, PRIMARY KEY), `product_name`, `category`, `price`.
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(100),
    category VARCHAR(50),
    price DECIMAL(10, 2)
);
-- customers: `customer_id` (INT, PRIMARY KEY), `first_name`, `last_name`, `email`,`phone_number`.
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(100),
    phone_number VARCHAR(20)
);
-- sales: `sale_id` (INT, PRIMARY KEY), `product_id` (INT), `customer_id` (INT), `sale_date`,`quantity`, `total_amount`
CREATE TABLE sales (
    sale_id INT PRIMARY KEY,
    product_id INT,
    customer_id INT,
    sale_date DATE,
    quantity INT,
    total_amount DECIMAL(10, 2)
);
-- payments: `payment_id` (INT, PRIMARY KEY), `sale_id` (INT), `payment_method`,`payment_date`, `amount_paid`.
CREATE TABLE payments (
    payment_id INT PRIMARY KEY,
    sale_id INT,
    payment_method VARCHAR(50),
    payment_date DATE,
    amount_paid DECIMAL(10, 2)
);

							-- QUESTION 2: 2. Data Insertion
-- Insert at least 10 products into the `products` table.
INSERT INTO products (product_id, product_name, category, price) VALUES
(1, 'Laptop', 'Electronics', 900000.00),
(2, 'Iphone 16', 'Electronics', 1000000.00),
(3, 'shirt', 'Clothing', 19000.00),
(4, 'Jeans', 'Clothing', 30000.00),
(5, 'Shoes', 'Footwear', 6000.00),
(6, 'cy goes to school', 'Books', 5000.00),
(7, 'ps4', 'Games', 100000.00),
(8, 'Toy', 'Toys', 15000.00),
(9, 'Watch', 'Accessories', 10000.00),
(10, 'Laptop Bag', 'Accessories', 50000.00);


-- Insert at least 40 customers into the `customers` table.
INSERT INTO customers (customer_id, first_name, last_name, email, phone_number) VALUES
(1,'Olonisakin','Emmanuel','emmanuelk5@gmail.com','08183691814'),
(2,'Olaoluwa', 'Faith', 'faitho@gmail.com', '09029458321'),
(3, 'Akinde', 'Happiness', 'Akindeh@gmail.com', '08049385763'),
(4, 'Fabunmi', 'praise',  'fabunmip@gmail.com', '09039299570'),
(5, 'Ajiboye', 'faith', 'ajiboyef2gmail.com', '09063286754'),
(6, 'Frank', 'Wilson', 'frankwilson@gmail.com','090324567'),
(7, 'Grace', 'Carter',  'gracecarter@gmail.com', '08039284039'),
(8, 'Henry', 'Miller',  'henrymiller@gmail.com', '09047589382'),
(9, 'Isabella', 'Taylor', 'isabellataylor@gmail.com', '09029847503'),
(10, 'Jack', 'Harris','jackharris@gmai.com', '09068932958'),
(11, 'Kate', 'Jones','katejones@gmai.com', '08034958432'),
(12, 'Liam', 'Martin',  'liammartin@gmai.com', '08055179669'),
(13, 'Maya', 'Garcia', 'mayagarcia@gmai.com', '09123498576'),
(14, 'Noah', 'Baker', 'noahbaker@gmai.com', '09049302943'),
(15, 'Olivia', 'Allen', 'oliviaallen@gmai.com', '09049380984'),
(16, 'Paul', 'Carter', 'paulcarter@gmai.com', '09059485321'),
(17, 'Quinn', 'Davis', 'quinndavis@gmai.com', '09089756432'),
(18, 'Riley', 'Wilson','rileywilson@gmai.com', '08095843219'),
(19, 'Sophia', 'Carter',  'sophiacarter@gmai.com', '09084738490'),
(20, 'Thomas', 'Miller',  'thomasmiller@gmai.com', '09085743285'),
(21, 'Uma', 'Taylor',  'umataylor@gmai.com', '08127348573'),
(22, 'Vincent', 'Harris','vincentharris@gmai.com', '09083948593'),
(23, 'Willow', 'Jones', 'willowjones@gmai.com', '08129384509'),
(24, 'Xavier', 'Martin', 'xaviermartin@gmai.com', '09039485634'),
(25, 'Yara', 'Garcia', 'yaragarcia@gmai.com', '08139485675'),
(26, 'Zachary', 'Baker',  'zacharybaker@gmai.com', '09029385793'),
(27, 'Abigail', 'Allen','abigailallen@gmai.com', '081942209584'),
(28, 'Benjamin', 'Carter','benjamincarter@gmai.com', '08120948357'),
(29, 'Chloe', 'Davis', 'chloedavis@gmai.com', '08029389342'),
(30, 'Daniel', 'Wilson','danielwilson@gmai.com', '09039847209'),
(31, 'Elijah', 'Carter', 'elijahcarter@gmail.com', '09038290187'),
(32, 'Amelia', 'Barnes', 'ameliaBarnes@gmail.com', '09069504932'),
(33, 'Aiden', 'Wright', 'aidenwright@gmail.com', '08183698833'),
(34, 'Evelyn', 'Scott', 'evelynscott@gmail.com', '08129304852'),
(35, 'Lucas', 'Torres', 'lucasTorres@gmail.com', '090294059642'),
(36, 'Harper', 'Kelly', 'harperkelly@gmail.com', '08059345067'),
(37, 'Logan', 'Bennett', 'loganbennett@gmail.com', '08096509310'),
(38, 'Abigail', 'Wood', 'abigailwood@gmail.com', '09019238704'),
(39, 'Jack', 'Reynolds', 'jackreynolds@gmail.com', '08049201953'),
(40, 'Avery', 'Flores', 'averyflores@gmail.com', '09150697402');

-- Insert at least 20 records into the `sales` table, making sure some customers buy multiple products.
INSERT INTO sales (sale_id, product_id, customer_id, sale_date, quantity, total_amount) VALUES
(1, 1, 11, '2024-10-15', 1, 900000.00),
(2, 2, 12, '2024-10-16', 2, 2000000.98),
(3, 3, 13, '2024-10-17', 3, 57000.00),
(4, 4, 14, '2024-10-18', 1, 30000.00),
(5, 5, 15, '2024-10-19', 2, 12000.00),
(6, 6, 16, '2024-10-20', 1, 50000.00),
(7, 7, 17, '2024-10-21', 1, 100000.00),
(8, 8, 18, '2024-10-22', 2, 30000.00),
(9, 9, 19, '2024-10-23', 1, 10000.00),
(10, 10, 20, '2024-10-24', 2, 100000.00),
(11, 1, 11, '2024-10-25', 2, 1800000.00), 
(12, 2, 12, '2024-10-26', 1, 1000000.00),
(13, 3, 13, '2024-10-27', 5, 95000.00), 
(14, 4, 14, '2024-10-28', 3, 90000.00),
(15, 5, 15, '2024-10-29', 1, 6000.00),
(16, 6, 16, '2024-10-30', 2, 10000.00),
(17, 7, 17, '2024-10-31', 3, 300000.00),
(18, 8, 18, '2024-11-01', 1, 15000.00),
(19, 9, 19, '2024-11-02', 2, 20000.00),
(20, 10, 20, '2024-11-03', 1, 50000.00);

-- Insert payment records corresponding to the sales, with varying amounts and dates.
INSERT INTO payments (payment_id, sale_id, payment_method, payment_date, amount_paid) VALUES
(1, 1, 'Credit Card', '2024-10-20', 90000.00),
(2, 2, 'Cash', '2024-10-21', 1000000.00),
(3, 3, 'Debit Card', '2024-10-22', 19000.00),
(4, 4, 'Check', '2024-10-23', 30000.00),
(5, 5, 'Credit Card', '2024-10-24', 6000.00),
(6, 6, 'Cash', '2024-10-25', 5000.00),
(7, 7, 'Debit Card', '2024-10-26', 100000.00),
(8, 8, 'Check', '2024-10-27', 15000.00),
(9, 9, 'Credit Card', '2024-10-28', 10000.00),
(10, 10, 'Cash', '2024-10-29', 50000.00),
(11, 11, 'Credit Card', '2024-10-30', 3000000.00),
(12, 12, 'Debit Card', '2024-10-31', 50000.00),
(13, 13, 'Check', '2024-11-01', 500000.00),
(14, 14, 'Credit Card', '2024-11-02', 20000.00),
(15, 15, 'Cash', '2024-11-03', 80000.00),
(16, 16, 'Debit Card', '2024-11-04', 25000.00),
(17, 17, 'Check', '2024-11-05', 300000.00),
(18, 18, 'Credit Card', '2024-11-06', 14000.00),
(19, 19, 'Cash', '2024-11-07', 200000.00),
(20, 20, 'Debit Card', '2024-11-08', 38000.00);

              -- QUESTION 3: Analysis Using SQL Concepts
	--  GROUP BY:
-- Write a query to calculate the total quantity sold for each product category
SELECT p.category, SUM(s.quantity) AS total_quantity_sold
FROM products p
INNER JOIN sales s 
ON p.product_id = s.product_id
GROUP BY p.category;

-- Write a query to count the number of sales for each customer.
SELECT c.customer_id, COUNT(s.sale_id) AS number_of_sales
FROM customers c
INNER JOIN sales s 
ON c.customer_id = s.customer_id
GROUP BY c.customer_id;

--  Write a query to find the total revenue generated by each payment method
SELECT p.payment_method, SUM(p.amount_paid) AS total_revenue
FROM payments p
GROUP BY p.payment_method;


    -- ORDER BY:                      
-- Write a query to retrieve a list of products, sorted by price in descending order.
SELECT product_id, product_name, price
FROM products
ORDER BY price DESC;

-- Write a query to get the sales records ordered by `sale_date` in ascending order.
SELECT sale_id, product_id, customer_id, sale_date, quantity, total_amount
FROM sales
ORDER BY sale_date ASC;

--  Write a query to display customers sorted by their last name alphabetically.
SELECT customer_id, first_name, last_name, email, phone_number
FROM customers
ORDER BY last_name ASC;

 -- HAVING CLAUSE:
-- Write a query to find products that have been sold more than 5 times, using `HAVING` with the`GROUP BY` statement.
SELECT p.product_id, p.product_name, SUM(s.quantity) AS total_quantity_sold
FROM products p
INNER JOIN sales s ON p.product_id = s.product_id
GROUP BY p.product_id, p.product_name
HAVING SUM(s.quantity) >5;

--  Write a query to list customers who have made total purchases (sum of `total_amount`) exceeding $100.
SELECT c.customer_id, c.first_name, c.last_name, SUM(s.total_amount) AS total_spent
FROM customers c
INNER JOIN sales s 
ON c.customer_id = s.customer_id
GROUP BY c.customer_id, c.first_name, c.last_name
HAVING SUM(s.total_amount) > 100000;

-- Write a query to find categories with a total sales revenue greater than $500
SELECT p.category, SUM(s.total_amount) AS total_revenue
FROM products p
INNER JOIN sales s ON p.product_id = s.product_id
GROUP BY p.category
HAVING SUM(s.total_amount) > 600000;


-- LIMIT CLAUSE:
-- Write a query to display the top 5 most expensive products.
SELECT product_id, product_name, price
FROM products
ORDER BY price DESC
LIMIT 5;

-- Write a query to display the 3 most recent sales.
SELECT sale_id, product_id, customer_id, sale_date, quantity, total_amount
FROM sales
ORDER BY sale_date DESC
LIMIT 3;

-- Write a query to list the first 5 customers who made purchases.
SELECT DISTINCT c.customer_id, c.first_name, c.last_name, s.sale_date
FROM customers c
INNER JOIN sales s 
ON c.customer_id = s.customer_id
ORDER BY s.sale_date ASC
LIMIT 5;


-- ALIASING:

-- Write a query to calculate the total revenue (sum of `total_amount`) for each product and use an alias `total_revenue` for the calculated field.
SELECT p.product_id, p.product_name, SUM(s.total_amount) AS total_revenue
FROM products p
INNER JOIN sales s 
ON p.product_id = s.product_id
GROUP BY p.product_id, p.product_name;

-- Write a query to display each customer's full name as `customer_name` by concatenating `first_name` and `last_name`.
SELECT c.customer_id, CONCAT(c.first_name, ' ', c.last_name) AS customer_name
FROM customers c;

-- Use aliasing to create a column called `sales_value` representing the product of `price` and`quantity` for each sale.
SELECT s.sale_id, s.product_id, s.quantity, p.price, (s.quantity * p.price) AS sales_value
FROM sales s
INNER JOIN products p
 ON s.product_id = p.product_id;

    -- String Functions: 
 -- Write a query to display the product names in uppercase.
 SELECT UPPER(product_name) AS product_name_uppercase
FROM products;

-- Write a query to extract the domain from the `email` field of each customer.
SELECT SUBSTRING_INDEX(email, '@', -1) AS email_domain
FROM customers;

-- Write a query to display the first three characters of each customer's `last_name`.
SELECT LEFT(last_name, 3) AS first_3_chars
FROM customers;

-- Write a query that trims extra spaces around product names and displays them.
SELECT TRIM(product_name) AS trimmed_product_name
FROM products;

      -- Aggregate Functions:
-- Write a query to calculate the average price of all products.
SELECT AVG(price) AS average_price
FROM products;

--  Write a query to find the maximum `total_amount` from the `sales` table.
SELECT MAX(total_amount) AS maximum_total_amount
FROM sales;

-- Write a query to calculate the total amount paid for all sales.
SELECT SUM(total_amount) AS total_amount_paid
FROM sales;

-- Write a query to calculate the minimum and maximum sale quantities.
SELECT MIN(quantity) AS minimum_quantity, MAX(quantity) AS maximum_quantity
FROM sales;

-- Write a query to determine the number of distinct product categories available.
SELECT COUNT(DISTINCT category) AS number_of_categories
FROM products;

-- Write a query to identify the customer with the highest total purchase amount.
SELECT c.customer_id, c.first_name, c.last_name, SUM(s.total_amount) AS total_spent
FROM customers c
INNER JOIN sales s 
ON c.customer_id = s.customer_id
GROUP BY c.customer_id, c.first_name, c.last_name
ORDER BY SUM(s.total_amount) DESC
LIMIT 1;

-- Calculate the total number of products sold for each product category and sort the result in descending order.
SELECT p.category, SUM(s.quantity) AS total_quantity_sold
FROM products p
INNER JOIN sales s
 ON p.product_id = s.product_id
GROUP BY p.category
ORDER BY SUM(s.quantity) DESC;

-- Write a query that retrieves the details of sales made in the last 30 days.
SELECT *
FROM sales
WHERE sale_date >= DATE_SUB(CURDATE(), INTERVAL 30 DAY);

-- Create a query to display the top 3 customers with the most sales in terms of quantity.
SELECT c.customer_id, c.first_name, c.last_name, SUM(s.quantity) AS total_quantity_sold
FROM customers c
INNER JOIN sales s ON c.customer_id = s.customer_id
GROUP BY c.customer_id, c.first_name, c.last_name
ORDER BY SUM(s.quantity) DESC
LIMIT 3;

-- Write a query to list all customers whose names start with the letter "J".
SELECT *
FROM customers
WHERE first_name LIKE 'J%';

-- Write a query to calculate the total unpaid amount for each sale by subtracting `amount_paid` from `total_amount`.
SELECT sale_id, total_amount - amount_paid AS unpaid_amount
FROM sales;
-- Write a query to find sales where the payment method was "Credit Card" and the `total_amount` is greater than $50.
SELECT *FROM payments
WHERE payment_method = 'Credit Card' AND amount_paid > 50000;

-- Write a query that lists all sales made by customers whose last names contain the letter "e".
SELECT *
FROM sales
INNER JOIN customers 
ON sales.customer_id = customers.customer_id
WHERE customers.last_name LIKE '%e%';
