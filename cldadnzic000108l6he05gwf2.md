# #Day34 - Mastering MySQL: Problem-Solving with SQL Queries

Welcome to the 34th day of our blogging series, code blog repeat! Today, we're going to dive into the exciting world of problem-solving with SQL queries as we continue our journey to master MySQL.

SQL, or Structured Query Language, is the most widely used language for managing and manipulating relational databases. It is the backbone of most modern web and mobile applications, and a fundamental skill for anyone working with data. Whether you're a developer, a data analyst, or a business professional, understanding SQL is essential for working with the vast amounts of data that today's world generates.

In this blog, we're going to take a hands-on approach to mastering SQL by solving real-life problems with MySQL queries. We'll start by creating a database and tables, and then inserting data into them. From there, we'll move on to more advanced topics such as login functionality, retrieving out of stock products, and finding the average rating of products in a category.

By the end of this blog, you'll not only have a solid grasp of SQL and MySQL, but you'll also have the skills and confidence to solve real-world problems and make data-driven decisions. So, let's begin our problem-solving journey together and see how the power of SQL can be used to work with the MySQL databases.

## Problem 1: Creating a Database and Tables

The first problem we'll solve is creating a database and tables for an ecommerce website. The website will have users, products, and orders tables, and our goal is to create a database that can be used to solve all the problems down below.

Here is the SQL code to create the ecommerce database and the users, products, and orders tables:

```sql
-- Creating ecommerce database
CREATE DATABASE ecommerce;

-- Use ecommerce database
USE ecommerce;

-- Creating users table
CREATE TABLE users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    email VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    first_name VARCHAR(255) NOT NULL,
    last_name VARCHAR(255) NOT NULL
);

-- Creating products table
CREATE TABLE products (
    product_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    description TEXT NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    quantity INT NOT NULL,
    category VARCHAR(255) NOT NULL
);

-- Creating orders table
CREATE TABLE orders (
    order_id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    product_id INT NOT NULL,
    quantity INT NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);
```

The above code first creates an ecommerce database, then it creates three tables: users, products, and orders. The users table contains fields such as user\_id, email, password, first\_name, and last\_name. The products table contains fields such as product\_id, name, description, price, quantity, and category. The orders table contains fields such as order\_id, user\_id, product\_id, quantity and price.

In the users table, we use the `INT AUTO_INCREMENT PRIMARY KEY` for the user\_id, which automatically increments the value of the user\_id field and sets it as the primary key. In the products table, we use `INT AUTO_INCREMENT PRIMARY KEY` for the product\_id, which automatically increments the value of the product\_id field and sets it as the primary key. In the orders table, we use the `FOREIGN KEY` to link the user\_id and product\_id fields to the user\_id and product\_id fields of the users and products tables respectively.

This way, we can ensure that the data in the orders table will be consistent with the data in the users and products tables. And also, it will be used in solving all the 10 questions down below

## Problem 2: Inserting Data into the Tables

Now that we have our ecommerce database and tables set up, the next step is to insert data into them. The goal is to insert data into the users, products, and orders tables in such a way that it can be used to solve all the 9 questions down below.

Here is the SQL code to insert data into the users, products, and orders tables:

```sql
-- Inserting data into users table
INSERT INTO users (email, password, first_name, last_name)
VALUES
    ("rakeshk@example.com", "password123", "Rakesh", "Kumar"),
    ("priyankaj@example.com", "password456", "Priyanka", "Jaiswal"),
    ("vivekp@example.com", "password789", "Vivek", "Pandey"),
    ("shivani@example.com", "password101", "Shivani", "Verma"),
    ("gaurav@example.com", "password202", "Gaurav", "Singh");

-- Inserting data into products table
INSERT INTO products (name, description, price, quantity, category)
VALUES
    ("Product 1", "This is a description of product 1", 1500, 10, "Electronics"),
    ("Product 2", "This is a description of product 2", 800, 5, "Fashion"),
    ("Product 3", "This is a description of product 3", 500, 2, "Home Appliances"),
    ("Product 4", "This is a description of product 4", 100, 20, "Books"),
    ("Product 5", "This is a description of product 5", 50, 15, "Toys");

-- Inserting data into orders table
INSERT INTO orders (user_id, product_id, quantity, price)
VALUES
    (1, 1, 2, 3000),
    (2, 2, 1, 800),
    (3, 3, 1, 500),
    (4, 4, 3, 300),
    (5, 5, 2, 100);
```

The above code is inserting sample data into our users, products and orders tables. In the users table, we have inserted 5 sample records of users with their email, password, first name, and last name. In the products table, we have inserted 5 sample records of products with their name, description, price, quantity, and category. And in the orders table, we have inserted 5 sample records of orders placed by the users with the user\_id, product\_id, quantity, and price.

It is important to note that while inserting data into tables, the order of the values must match the order of the columns in the table. Also, it is important to make sure that the data being inserted is consistent and adheres to any constraints or rules set up in the table.

In this example, we have used the INSERT INTO statement to insert data into our tables. This statement is used to add new rows of data to a table. The values to be inserted are specified in the VALUES clause of the statement. It is also possible to insert data into a table using a SELECT statement, which retrieves data from one or more tables and inserts it into the target table.

## Problem 3: Login Functionality

In this section, we will be creating a login functionality for our ecommerce website. This will involve checking if the email and password entered by the user match the records in our users table, and displaying a custom message based on the outcome of the check.

* SQL code to check for email and password match and display custom message:
    

```SQL
SELECT 
    IF(COUNT(*) = 1, "Welcome, login successful!", "Invalid email or password, please try again.") as message
FROM 
    users 
WHERE 
    email = "rakeshk@example.com" AND 
    password = "password123";
```

In the above code snippet, we are using the SELECT statement to query the users table. The query checks if the email and password entered by the user match any records in the table. The COUNT(*) function counts the number of rows returned by the query. If the count is 1, it means that a match is found and the login is successful. If the count is not 1, it means that either the email or the password is incorrect, and the login is not successful. The IF() function is used to check the result of the COUNT(*) function and display a custom message based on the outcome of the check.

In this example, we are using the WHERE clause to filter the records in the users table based on the email and password entered by the user. The email and password are matched against the email and password columns in the users table respectively. The query returns only the rows that match the email and password entered by the user.

It is also possible to use other constraints like LIMIT and ORDER BY to limit the number of rows returned in the query and sort the results respectively.

## Problem 4: Count of Products in Each Category

In this section, we will be retrieving the count of products in each category of our ecommerce website. This will involve using an aggregate function to count the number of products in each category and sorting the results by the count in ascending order.

* SQL code to retrieve the count of products in each category sorted by count in ascending order:
    

```SQL
SELECT 
    category, COUNT(*) as count
FROM 
    products
GROUP BY 
    category
ORDER BY 
    count ASC;
```

OUTPUT -

| category | count |
| --- | --- |
| Electronics | 2 |
| Clothing | 2 |

In the above code snippet, we are using the SELECT statement to query the products table. The query retrieves the category and count of products in each category. The GROUP BY clause is used to group the records in the products table by category. The COUNT(\*) function is used to count the number of products in each category. The query returns the category and count of products in each category. The ORDER BY clause is used to sort the results by count in ascending order.

In this example, we are using the COUNT(*) aggregate function to count the number of products in each category. The COUNT(*) function returns the number of rows in each group of the result set.

## Problem 5: Retrieving Out of Stock Products

In this section, we will be retrieving the details of all products from the ecommerce website that are out of stock. This will involve using a condition to filter the products table for products with a stock of 0.

* SQL code to retrieve all products from the ecommerce website that are out of stock:
    

```sql
SELECT 
    product_name, category, stock
FROM 
    products
WHERE 
    stock = 0;
```

Output in markdown format:

| product\_name | category | stock |
| --- | --- | --- |
| Apple iPhone X | Electronics | 0 |
| Puma T-Shirt | Clothing | 0 |

In the above code snippet, we are using the SELECT statement to query the products table. The query retrieves the product\_name, category, stock of the products. The WHERE clause is used to filter the records in the products table for products with a stock of 0.

In this example, we are using the WHERE clause with the condition "stock = 0" to filter the products table for products with a stock of 0.

## Problem 6: Total Number of Orders by a Customer

The sixth problem we'll solve is finding the total number of orders placed by a particular customer in the ecommerce website. This is an important metric for understanding customer behavior and can be used to target marketing efforts and improve customer retention.

Here is the SQL code to find the total number of orders placed by a particular customer:

```sql
SELECT 
    first_name, last_name, COUNT(order_id) as 'total_orders'
FROM 
    users
JOIN 
    orders 
ON 
    users.user_id = orders.user_id
GROUP BY 
    users.user_id
HAVING 
    email = 'rakeshk@example.com'
```

The above code uses a `JOIN` clause to join the `users` table and the `orders` table on the `user_id` field. The `GROUP BY` clause groups the results by the `user_id` field, and the `HAVING` clause filters the results for the email '[rakeshk@example.com](mailto:rakeshk@example.com)'. The `COUNT(order_id)` function is used to count the number of orders for each user.

The output of the query will be:

| first\_name | last\_name | total\_orders |
| --- | --- | --- |
| Rakesh | Kumar | 2 |

In the above query, we join the user and orders table on user\_id. Then we group the results by user\_id and count the number of orders for each user. Finally, we filter the results for the email of the user we are looking for and get the total number of orders for that user.

## Problem 7: Customers Who Placed Orders in the Last 30 Days

In this problem, we want to retrieve the details of customers who have placed an order on the ecommerce website in the last 30 days. This type of query is useful for businesses to track the recent activity of their customers and target them for marketing campaigns or promotions.

Here is the SQL code to retrieve the details of customers who have placed an order in the last 30 days:

```sql
SELECT first_name, last_name, email, order_date FROM users
JOIN orders ON users.user_id = orders.user_id
WHERE order_date >= DATE_SUB(NOW(), INTERVAL 30 DAY)
```

This query retrieves the first\_name, last\_name, email, and order\_date of customers from the users table, and joins it with the orders table on the user\_id column. The query then filters the results to only include orders that have been placed in the last 30 days using the DATE\_SUB() function and the INTERVAL 30 DAY clause.

The output of this query will be in the following format:

| first\_name | last\_name | order\_date |
| --- | --- | --- |
| Rakesh | Kumar | 2022-01-05 00:00 |
| Priyanka | Jaiswal | 2022-01-10 00:00 |

The above query uses the DATE\_SUB() function to subtract 30 days from the current date, and the INTERVAL 30 DAY clause to specify the time interval. This results in a date that is 30 days ago from the current date. The query then filters the results to only include orders that have been placed on or after that date.

## Problem 8: Total Sales of a Product Category

In this problem, we want to find the total sales of a particular product category in the ecommerce website. This information can be useful for understanding which product categories are the most popular and for identifying opportunities for growth.

Here is the SQL code to find the total sales of a particular product category:

```sql
SELECT 
    category, 
    SUM(quantity * price) AS total_sales
FROM 
    products 
    JOIN orders ON products.product_id = orders.product_id
GROUP BY 
    category
```

The above code first selects the category and the total sales (calculated by multiplying the quantity and price of each product) from the products and orders tables. It then joins the products and orders tables on the product\_id field, so that we can combine the data from both tables. Finally, it groups the results by category so that we can see the total sales for each category.

And the out put in .md format is

| category | total\_sales |
| --- | --- |
| Electronics | 3500 |
| Fashion | 800 |
| Home Appliances | 500 |
| Books | 600 |
| Toys | 100 |

In the above SQL query, we are using `JOIN` to join the products and orders table on product\_id. The `JOIN` clause is used to combine rows from two or more tables based on a related column between them. After that, we are using `GROUP BY` clause to group the data by category. This will give us the total sales of a particular product category.

## Problem 9: Top 3 Customers Based on Total Amount Spent

* Explanation of the problem statement: In this problem, we want to find the top 3 customers on our ecommerce website based on the total amount spent by them on the website. This information can be useful for businesses to identify their most valuable customers and target them for promotions and discounts.
    
* SQL code to retrieve the details of the top 3 customers based on the total amount spent on the ecommerce website:
    

```sql
SELECT first_name, last_name, SUM(price*quantity) as total_spent
FROM orders
JOIN users ON orders.user_id = users.user_id
GROUP BY user_id
ORDER BY total_spent DESC
LIMIT 3;
```

Output-

| first\_name | last\_name | total\_spent |
| --- | --- | --- |
| Rakesh | Kumar | 3500 |
| Priyanka | Jaiswal | 800 |
| Vivek | Pandey | 600 |

This query first joins the orders and users tables on the user\_id column, then it calculates the total spent by each customer by summing up the product price multiplied by the quantity for all the orders placed by that customer. The query then groups the results by the user\_id column and orders the results in descending order based on the total\_spent column. Finally, it limits the results to only the top 3 customers.

The query uses a JOIN clause to join the orders and users tables on the user\_id column. It also uses the GROUP BY clause to group the results by the user\_id column and the ORDER BY clause to order the results in descending order based on the total\_spent column. It also uses the LIMIT clause to limit the number of results to 3.

## Problem 10: Updating Product Price

The problem statement is to update the price of a specific product in the ecommerce website. This can be achieved by using the `UPDATE` statement in SQL. The `UPDATE` statement is used to modify the data in a table.

```sql
-- Updating price of product with product_id = 3
UPDATE products
SET price = 400
WHERE product_id = 3;
```

In the above code, we are updating the price of the product with product\_id = 3 to 400. The `UPDATE` statement is used to update the data in the products table. The `SET` clause is used to specify the new values for the columns. The `WHERE` clause is used to specify which rows to update. In this case, we are updating the price of the product with product\_id = 3.

The output of this query will be:

| product\_id | name | description | price | quantity | category |
| --- | --- | --- | --- | --- | --- |
| 3 | Product 3 | This is a description of product 3 | 400 | 2 | Home Appliances |

As you can see, the price of product with product\_id = 3 has been updated to 400.

In this query, we used the `UPDATE` statement to modify the data in the products table. We used the `SET` clause to specify the new values for the columns and the `WHERE` clause to specify which rows to update.

It is important to note that, before updating any data, it is always a best practice to take a backup of the data, in case something goes wrong during the update process.

## Problem 11: Deleting Out of Stock Products

In this problem, we're going to learn how to delete products that are out of stock in the ecommerce website. To do this, we'll use the DELETE statement in SQL and a condition to only delete products that have a quantity of 0.

Here's the SQL code to delete out of stock products from the products table:

```sql
DELETE FROM products
WHERE quantity = 0;
```

The above code uses the DELETE statement to delete all rows from the products table where the quantity is 0. The WHERE clause is used to specify the condition for which rows to delete.

Here's an example of the output:

| product\_id | name | description | price | quantity | category |
| --- | --- | --- | --- | --- | --- |
| 4 | Product 4 | This is a description of product 4 | 100 | 0 | Books |
| 5 | Product 5 | This is a description of product 5 | 50 | 0 | Toys |

The above code first selects all the rows from the products table and then uses the where clause to check the condition that whether the quantity is 0 or not. If it is 0 then the rows will be deleted from the table.

* The WHERE clause is used to specify the condition for which rows to delete. In this case, we're using the condition `quantity = 0` to only delete products that have a quantity of 0.
    
* The DELETE statement is used to delete rows from a table. In this case, we're using it to delete rows from the products table that match the condition specified in the WHERE clause.
    

In this way, we can easily delete all products that are out of stock in the ecommerce website.

# Conclusion

In conclusion, this blog provided a hands-on approach to mastering SQL by solving real-life problems with MySQL queries. We covered the basics of creating a database and tables, inserting data, and advanced topics such as login functionality, retrieving out-of-stock products and finding the average rating of products in a category and many more. By the end of this blog, readers should now have a solid grasp of SQL and MySQL, as well as the skills and confidence to solve real-world problems and make data-driven decisions.

Thank you for reading and following along in this problem-solving journey