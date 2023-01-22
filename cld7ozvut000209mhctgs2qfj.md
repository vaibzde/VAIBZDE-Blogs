# #Day33 - Introduction to MySQL


Welcome to the 33rd day of our "50 Day Quest for Backend Mastery" blog series! Today, we will be diving into the exciting world of MySQL, a popular open-source relational database management system. We have previously discussed the importance of databases and different types of database systems, and now it's time to take a closer look at MySQL. You'll learn about its uses and why it's a popular choice among developers and businesses. Join us as we explore the ins and outs of MySQL and discover how it can take your projects to the next level. Get ready to learn in a fun and engaging manner, and let's start our journey with MySQL!

# Introduction to MySQL

**Definition**: MySQL is a popular open-source relational database management system (RDBMS). It is used for managing and storing data in a structured manner.

Simply,
-   MySQL is a type of computer software called a database. It is used to store and organize information, like names and addresses.
-   Think of it like a big digital notebook, where you can put all your important information and easily find it later.
-   MySQL is often used for websites and apps, to keep track of all the user information and what pages they visit.
-   It is also used by businesses to store customer information, sales data, and more.
-   It is popular because it is free and easy to use.

**Key features:**

-   MySQL is easy to use and has a simple SQL syntax.
-   It is a robust and reliable system that can handle large amounts of data and multiple concurrent connections.
-   MySQL supports a wide range of programming languages and platforms, including PHP, Java, and C#.
-   It has built-in security features, such as password encryption and access controls, to protect the data.
-   MySQL provides various tools and utilities for managing and optimizing the performance of the database.
-   It is widely used in web development, data warehousing, and other applications that require fast and efficient data management.

# MySQL Architecture

Have you ever wondered how MySQL works behind the scenes? Well, in this section, we'll take a closer look at the architecture of MySQL and how it manages data storage and processes.

-   Client-Server Architecture: MySQL uses a client-server architecture, which means that the MySQL server software runs on a central computer, and clients connect to it to access and manage the data. The client can be a program like PHP or a tool like the MySQL Workbench. This architecture allows multiple users to connect to the server and access the data at the same time.
    
-   MySQL Data Storage: MySQL stores data in tables, which are similar to spreadsheets. Each table has rows (also called records) and columns (also called fields). This structure allows for easy organization and retrieval of data. MySQL stores the tables on a storage device, like a hard drive.
    
-   MySQL Processes and Threads: When a client sends a request to the MySQL server, the server creates a process or thread to handle the request. A process is like a mini-program that runs inside the MySQL server software, and a thread is a smaller unit of a process. Each process or thread handles one request at a time. This allows MySQL to handle multiple requests simultaneously, making it more efficient.
    

In simple terms, MySQL's architecture is designed to handle multiple client connections and manage data storage and processes efficiently. The client-server architecture allows multiple users to access the data simultaneously, data is stored in tables for easy organization and retrieval, and processes and threads handle requests efficiently. With this architecture in place, MySQL can handle large amounts of data and multiple concurrent connections.

# Installing and Configuring MySQL

Installing and configuring MySQL is the first step in using it for your projects. Here is a short overview of the process:

1.  Download the MySQL installer from the official website ([https://dev.mysql.com/downloads/installer/](https://dev.mysql.com/downloads/installer/)) and run the installer.
2.  Follow the prompts to install MySQL on your computer.
3.  After installation, open the MySQL command-line client or MySQL Workbench to access the MySQL server.
4.  Use the command "mysql_secure_installation" to secure your MySQL installation.
5.  To configure MySQL, you will need to edit the configuration file (my.cnf) and set parameters such as the server's hostname, port number, and memory usage.
6.  You can also create and manage databases and users using the command-line client or MySQL Workbench.

You can refer to the official MySQL documentation ([https://dev.mysql.com/doc/](https://dev.mysql.com/doc/)) for detailed instructions on installing and configuring MySQL on your operating system.

# MySQL Queries

MySQL uses a language called SQL (Structured Query Language) to interact with the databases. Queries are used to retrieve, update, and manipulate the data in a database. MySQL supports several types of queries, including:
1.  Data Definition Language (DDL
2.  Data Manipulation Language (DML)
3.  Data Query Language (DQL)
4.  Data Control Language (DCL
5.  Transaction Control Language (TCL)

## Data Definition Language (DDL)

DDL is a set of SQL commands used to define the database schema. It deals with descriptions of the database schema and is used to create, modify, and delete the structure of database objects in the database. Some common examples of DDL statements include `CREATE`, `ALTER`, `RENAME`, `TRUNCATE`, and `DROP`.

Creating, altering, renaming, truncating and dropping tables and other database objects

-   `CREATE TABLE` is used to create a new table in the database. For example, the following SQL statement creates a new table named "customers" with various columns:

```sql
CREATE TABLE customers (
    id INT PRIMARY KEY,
    name VARCHAR(255),
    address VARCHAR(255),
    city VARCHAR(255),
    country VARCHAR(255)
);

```

-   `ALTER TABLE` is used to alter the structure of a table. For example, the following SQL statement adds a new column named "email" to the "customers" table:

```sql
ALTER TABLE customers
ADD email VARCHAR(255);

```

-   `RENAME TABLE` is used to rename a table. For example, the following SQL statement renames the "customers" table to "clients":

```sql
RENAME TABLE customers TO clients;

```

- `TRUNCATE TABLE` is used to remove all the data from a table. For example, the following SQL statement removes all data from the "customers" table:

```sql
TRUNCATE TABLE customers;

```

- `DROP TABLE` is used to delete a table from the database. For example, the following SQL statement drops the "customers" table:

```sql
DROP TABLE customers;

```

It's worth noting that truncate and drop both remove all the data but truncate is faster than drop because it doesn't generate rollback information and it reset the auto increment value while drop table command delete the table permanently.

## Data Manipulation Language (DML)

DML is a set of SQL commands used to manage data within schema objects. Some common examples of DML statements include `SELECT`, `INSERT`, `UPDATE`, and `DELETE`.

Selecting, inserting, updating and deleting data

-   `SELECT` is used to retrieve data from one or more tables. For example, the following SQL statement selects all columns and rows from the "customers" table:

```sql
SELECT * FROM customers;
```

- `INSERT` is used to insert data into a table. For example, the following SQL statement inserts a new row into the "customers" table:

```sql
INSERT INTO customers (id, name, address, city, country)
VALUES (1, 'John Doe', '123 Main St', 'New York', 'United States');

```

- `UPDATE` is used to modify data in a table. For example, the following SQL statement updates the city of the customer with id 1 to 'Los Angeles':

```sql
UPDATE customers
SET city = 'Los Angeles'
WHERE id = 1;

```

- `DELETE` is used to delete data from a table. For example, the following SQL statement deletes the customer with id 1 from the "customers" table:

```js
DELETE FROM customers
WHERE id = 1;

```

## Data Query Language (DQL)

DQL is a set of SQL commands used to retrieve data from one or more tables. SELECT statement is used for data retrieval.

Retrieving data from one or more tables

-   `SELECT` is used to retrieve data from one or more tables. For example, the following SQL statement retrieves all columns and rows from the "customers" table where the country is 'United States':

```sql
SELECT * FROM customers
WHERE country = 'United States';

```

## Data Control Language (DCL)

DCL is a set of SQL commands used to create and manage database security and access control. Some common examples of DCL statements include `GRANT` and `REVOKE`.

Managing database security and access control

-   `GRANT` is used to grant access permissions to users or roles. For example, the following SQL statement grants the "SELECT" permission to the user "jane" on the "customers" table:

```sql
GRANT SELECT ON customers TO jane;

```

- `REVOKE` is used to revoke access permissions from users or roles. For example, the following SQL statement revokes the "SELECT" permission from the user "jane" on the "customers" table:

```sql
REVOKE SELECT ON customers FROM jane;

```

## Transaction Control Language (TCL)

TCL is a set of SQL commands used to manage transactions in the database. Some common examples of TCL statements include `COMMIT` and `ROLLBACK`.

Controlling transaction management in MySQL

-   `COMMIT` is used to save the changes made during a transaction to the database. For example, the following SQL statement commits the current transaction:

```sql
COMMIT;

```

- `ROLLBACK` is used to undo the changes made during a transaction. For example, the following SQL statement rolls back the current transaction:

```js
ROLLBACK;

```

It is important to note that in MySQL, the default storage engine, InnoDB, supports transaction and uses the above TCL statements to manage it. While MyISAM doesn't support transaction, so TCL statements will not have any effect.

> A transaction is a series of one or more database operations that are executed as a single unit of work. The operations can include inserting, updating, and deleting data, as well as creating, altering, and dropping database objects. A transaction is said to be atomic, meaning that it is indivisible and irreducible. This means that all the operations in a transaction will be executed or none of them will be executed.
> Transactions also have the properties of consistency, isolation, and durability (often referred to as the "ACID properties") - which we had discussed in our previous blog.

# FileSystem

A file system is a method of organizing and storing files on a storage device, such as a hard drive or solid-state drive. It allows for the retrieval of files in an organized manner by grouping them into directories and subdirectories, similar to a hierarchical tree structure. The file system also ensures consistency in the organization and management of files by providing methods for naming, searching, and organizing them. Some common file systems include NTFS, FAT32, and ext4.
Understanding the file system is important when working with databases because a database is essentially a collection of files stored on a storage device. The file system is responsible for managing and organizing these files, making sure that they are stored in an organized and consistent manner. Working with many database management systems rely on file system for storage, indexing, and backup

# Conclusion

In this blog post, we have covered a wide range of topics related to MySQL. We began with an introduction to MySQL, including its definition, key features, and its popularity among web developers and businesses. We then delved into the inner workings of MySQL, including its architecture and how it manages data storage and processes. We also covered different SQL queries such as DQL, DDL, DCL, and DTL, and discussed their functions. Overall, this blog post provided a comprehensive overview of MySQL, from its basic concepts to its advanced features.

We hope that this blog post was informative and helpful. We would appreciate any feedback or thoughts on your experiences with MySQL. 

> Happy coding!

