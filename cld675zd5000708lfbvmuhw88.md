# #Day32 - Comparing RDBMS and NoSQL - ACID Properties, Performance, Scaling Strategies, and Sharding

Welcome to the 32nd day of our series on back-end development! In this post, we'll explore the fundamental concepts and techniques of database management that are essential for building reliable and scalable back-end systems. We'll cover topics such as data models, ACID properties, performance characteristics, scaling options, and sharding, and we'll compare the ways in which relational database management systems (RDBMS) and NoSQL databases handle these concepts and techniques. Whether you are building a web application or working on a data-intensive project, understanding the strengths and limitations of different database systems is crucial for success in back-end development. Join us as we delve into the foundational concepts and techniques of database management and how they apply to back-end development.

# Understanding Foundational Concepts & Techniques in Database Management

## ACID Properties

Atomic properties are a critical aspect of database systems, as they help to ensure the integrity and consistency of data stored in the database. In the context of databases, the acronym CIDA (short for Consistency, Isolation, Durability, Atomicity) is often used to summarize the key properties required to ensure a database system's correct operation.

* Consistency refers to the requirement that the database must be in a valid state at all times. This means that data must conform to any constraints or rules that have been defined for the database, and that any changes to the data must not violate these constraints.
    
* Isolation refers to the ability of transactions to operate independently of each other. This is important for ensuring that the results of one transaction do not interfere with the results of another transaction.
    
* Atomicity refers to the indivisible nature of database transactions. A transaction is a series of database operations that are treated as a single unit of work, either being completed in its entirety or not at all. This is important for ensuring that the database remains in a consistent state, even in the event of errors or failures during the transaction.
    
* Durability refers to the requirement that once a transaction has been committed, its effects must be permanent. This means that the changes made by a transaction must be persisted to the database, even in the event of system failures or crashes.
    

Together, these properties (CIDA) help to ensure the reliability and integrity of data stored in a database system. They are essential for building systems that can handle large volumes of data and support complex business processes.

## Vertical Scaling & Horizontal Scaling

Scalability is an important concept in database systems, as it refers to the ability of the database to handle an increasing workload without a corresponding increase in response time. In other words, a scalable database is one that is able to handle a larger volume of data or a higher number of users without experiencing a decrease in performance.

Scalability is important for a variety of reasons. As the volume of data stored in a database grows, the demands on the database system also increase. If the database is not able to handle this increased workload, it can result in slower performance and reduced availability. This can be a major issue for businesses that rely on their database systems to support critical operations.

There are two main approaches to scaling a database system: vertical scaling and horizontal scaling.

* Vertical scaling involves increasing the resources (such as memory or processing power) of the database server. This can be achieved by upgrading the hardware or adding additional servers to the database cluster. Vertical scaling is a simple and straightforward approach, but it can be limited by the physical constraints of the hardware.
    
* Horizontal scaling, on the other hand, involves distributing the workload across multiple database servers. This can be achieved by partitioning the data across multiple servers, or by adding additional servers to the database cluster. Horizontal scaling is a more complex approach, but it allows a database to scale more effectively as the workload increases.
    

### Main difference in Horizontal and vertical Scaling

* Horizontal scaling means scaling by adding more machines to your existing infrastructure of resources (also described as “scaling out”)
    
* Vertical scaling refers to scaling by adding more power (e.g. CPU, RAM) to an existing machine (also described as “scaling up”)
    

One of the fundamental differences between the two is that horizontal scaling requires breaking a sequential piece  
of logic into smaller pieces so that they can be executed in parallel across multiple machines. In many respects,  
vertical scaling is easier because the logic really doesn’t need to change. Rather, you’re just running the same code  
on higher-spec machines. However, there are many other factors to consider when determining the appropriate  
approach.

## Sharding & Partition

Sharding is a powerful technique for optimizing database management systems, particularly in large-scale applications. By dividing data into smaller partitions, or "shards," you can improve the performance, scalability, and availability for your database.

There are two main types of sharding: vertical and horizontal.

* Vertical sharding involves dividing a database table into multiple tables, each containing the same number of rows but fewer columns. This is useful when queries tend to return only a subset of columns in the data. For example, if some queries request only names, and others request only addresses, then the names and addresses can be sharded onto separate servers.
    
* Horizontal sharding, on the other hand, involves dividing a table into multiple smaller tables, each containing the same number of columns but fewer rows. This is useful when queries tend to return a subset of rows that are often grouped together, such as when filtering data based on short date ranges. By horizontally scaling out, you can enable a flexible database design that increases performance by taking advantage of all the compute resources across your cluster for every query, and by reducing the number of rows each machine has to scan when responding to a query.
    

But sharding isn't just about performance. It can also improve the availability of your database. In the event of an outage on an unsharded database, the entire application becomes unusable. With a sharded database, only the portions of the application that relied on the missing shards are affected. And to further mitigate the impact of outages, you can replicate backup shards on additional nodes.

In short, sharding is a valuable tool for optimizing and scaling your database, and it can make a big difference in the performance and availability of your application.

## Joins in Database management system

In a database management system, a join is a way of combining data from two or more tables based on a common field or attribute. Joins are used to retrieve data from multiple tables in a single query, allowing users to pull data from multiple sources and view it as a single dataset. In a relational database management system (RDBMS), joins are an important tool for querying and manipulating data stored in multiple tables. RDBMS use structured query language (SQL) to perform joins. In a NoSQL database, the concept of joins may be handled differently. Some NoSQL databases, such as document-oriented databases.

# Comparison of NoSQL and RDBMS

| Comparison | RDBMS | NoSQL |
| --- | --- | --- |
| Data model | Relational model | Various data models (e.g. key-value, document, columnar) |
| ACID properties | Provides atomicity, consistency, isolation, and durability | May trade off some ACID properties for a more flexible data model and horizontal scaling |
| Performance | Dependent on disk subsystem, optimization of queries, indexes, and table structure required | Function of hardware, cluster size, network latency, and calling application |
| Scale | Typically scales up by increasing compute capabilities of hardware or scales out by adding replicas for read-only workloads | Typically scales horizontally using distributed architecture to increase throughput and provide consistent performance at near boundless scale |
| APIs | SQL-based | Document-based APIs allow app developers to use native data structures when retrieving data |
| Sharding | Manual sharding may be required to scale horizontally | Built-in sharding may be available depending on the database |

# Conclusion

In conclusion, database management is a critical aspect of back-end development and understanding the fundamental concepts and techniques is essential for building reliable and scalable systems. From the ACID properties to data models, scaling options and sharding, these concepts and techniques are the building blocks for designing and implementing a robust database system. It is important to understand the strengths and limitations of different data models and database systems, as this will help you make informed decisions on which one to use for your specific project. Additionally, understanding the concept of scalability and the different scaling options available is crucial for ensuring that your database system can handle the increasing workload as your business grows. Overall, by mastering the foundational concepts and techniques of database management, you will be well-equipped to build robust and reliable back-end systems that can handle large volumes of data and support complex business processes.