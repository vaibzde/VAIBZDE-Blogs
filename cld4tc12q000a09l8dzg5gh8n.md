# #Day31 - Understanding Databases System - NoSQL vs RDBMS

Welcome to the 31st day of our blogging series! Today, we will be diving into the topic of understanding database systems.

# Introduction

Databases are an essential part of modern technology. They are a collection of organized data that can be easily accessed, managed, and updated. The purpose of a database is to store and manage data in a way that is efficient and reliable.

Databases are used in a wide range of applications, such as online shopping, social media, and financial management. They play a crucial role in managing and processing large amounts of data and help to ensure data consistency and integrity. Without databases, these applications would not be able to function properly.

As an example, let's take a look at how social media platforms like Twitter use databases. Twitter receives a massive amount of data every second, including tweets, user information, and interactions. All of this data needs to be stored and organized in a way that is easily accessible and retrievable. This is where databases come in. Twitter uses databases to store all of this data and make it easily accessible to users. Without a database, it would be nearly impossible for Twitter to function and provide a seamless user experience.

In addition to storing data, databases also play an important role in data analysis and decision-making. For example, Twitter uses data from its databases to analyze user engagement and determine which content is most popular. This information is then used to improve the platform and provide a better experience for users.

As a backend developer, it's important to have a solid understanding of databases and how to interact with them. This includes understanding database design and implementation, as well as writing code to interact with the database. It's also important to understand how to optimize database performance and troubleshoot any issues that may arise.

In web development, databases play a crucial role. They allow for the storage and retrieval of data needed for web applications to function. Without a database, web applications would not be able to store user information or application data. This makes databases an essential part of any web development project.

# What a database system is?

A database system is a collection of data stored in a structured manner, along with a set of tools and programs to manage and manipulate that data. The purpose of a database system is to store and organize data in a way that is efficient, secure, and easy to access and update.

One of the main reasons for using a database system is to prevent data loss. Unlike data stored in a computer's memory (e.g. RAM), data stored in a database is persistent and remains even after the computer is turned off. This is because databases are typically stored on a hard drive or another permanent storage device.

Another reason for using a database system is to enable efficient data access and manipulation. A database management system (DBMS) is a software program that allows users to interact with the database and perform tasks such as inserting, updating, and retrieving data. A DBMS provides a variety of tools and functions to help users manage and analyze data, such as query languages, indexing, and data backup and recovery.

In Summary,

> A database system is a collection of data stored in a structured manner, along with a database management system (DBMS) that provides a variety of tools and functions to help users manage and analyze the data using a query language. The DBMS enables efficient and secure data access and manipulation, and helps to ensure the integrity and reliability of the data.

## Components of a database:

- Data: This is the actual information that is stored in the database, such as customer names, product information, and sales data. Data is organized into tables, which consist of rows and columns. Each table represents a specific subject, such as customers or products, and the columns represent the different attributes of that subject, such as name, address, and phone number.

- Software: This refers to the database management system (DBMS) software that is used to create, manage, and maintain the database. Examples of DBMS software include MySQL, SQL Server, Oracle, MongoDB, and PostgreSQL.

- Hardware: This refers to the physical components that are used to store the database, such as servers, storage devices, and network devices. The hardware must be powerful enough to support the demands of the database and the number of users accessing it.

- Data Access Language: This refers to the language or interface used to interact with the database, such as SQL (Structured Query Language) which is used to insert, update, retrieve and delete data in the database.

- Procedures: This refers to the set of instructions that are used to manage and maintain the database, such as backup procedures, security procedures, and performance tuning procedures. These procedures ensure the integrity, security, and performance of the database.


# Structured and Unstructured Data

In the context of database systems, there are two main types of data: structured data and unstructured data.

Different types of data, such as structured and unstructured data, require different database management systems to store and access them effectively, and understanding the strengths and limitations of these systems is important for choosing the right one for a given application or use case.

**Structured data** is data that is organized in a well-defined format, such as a table with rows and columns. Each row in the table represents a single record or entity, and each column represents a specific piece of information or attribute about that entity. Structured data is easy to search, sort, and analyze because it follows a fixed structure. Examples of structured data include customer records, product inventory lists, and financial transactions. Structured data is typically stored in a relational database management system (RDBMS) and can be queried using a structured query language (SQL).. The relational model is a data model that is commonly used for storing structured data.

**Unstructured data** is data that does not have a well-defined format or structure. It may include text documents, images, videos, audio files, and other types of media that do not fit neatly into a tabular format. Unstructured data is more difficult to search, sort, and analyze than structured data because it does not follow a fixed structure. Examples of unstructured data include emails, social media posts, and customer reviews. Unstructured data is typically stored in a NoSQL (not only SQL) database and is queried using a variety of methods, such as search queries or map-reduce functions. Some data models that can be used to store unstructured data include the document model, key-value model, and graph model.

Both structured and unstructured data are important for many modern applications and systems, and a combination of both types of data is often used to provide a comprehensive and accurate representation of real-world information and situations.

# Data Model

A data model is a way of organizing data in a database. It helps to structure the data in a logical and consistent manner and makes it easier to store, retrieve, and manipulate the data. Different data models are used for different types of data and are suitable for different use cases. For example, the relational model is a data model that is used for structured data, while the document model is a data model that is used for unstructured data. By understanding the different data models and their characteristics, you can choose the right one for your needs.

# Types of Data Base Systems

Database systems can be classified based on the data model they use, such as the relational model (used by RDBMSs for storing structured data) or NoSQL models (used by NoSQL databases for storing unstructured data), and examples of database systems in each category include RDBMSs (e.g. Oracle, MySQL) and NoSQL databases (e.g. MongoDB, Cassandra).

## Understanding Relational database management systems (RDBMS) & its Use Cases

A relational database management system (RDBMS) is a type of database management system that stores data in the form of related tables. Tables in a relational database are similar to tables in a spreadsheet, with rows representing individual records and columns representing data fields within each record. The relational model is a method of organizing data into tables of rows and columns, with the tables being known as relations, the rows being known as tuples, and the columns being known as attributes. SQL (Structured Query Language) is a programming language that is used to manipulate and manage data stored in an RDBMS. SQL is used to create, alter, and delete tables in a database, as well as to insert, update, and delete data within the tables.

Some common examples of RDBMS include MySQL, Oracle, and Microsoft SQL Server.

RDBMS are commonly used in a wide range of applications, including financial systems, customer relationship management systems, and online stores. RDBMS are used to store and manage large amounts of structured data, and they allow users to easily search and retrieve specific data, as well as to share data among multiple users and applications.

### Drawbacks of RDBMS

Some potential drawbacks of a relational database management system (RDBMS):

1. Complexity: RDBMS can be complex to set up and maintain, especially for large or highly-trafficked databases.
    
2. Limited scalability: RDBMS can struggle to scale to very large amounts of data or high levels of concurrent users.
    
3. Inflexible data model: The relational model is based on a fixed schema, meaning that the structure of the data must be defined in advance and cannot easily be changed once the database is in use. This can be inflexible and can make it difficult to accommodate changing business needs.
    
4. Poor performance for certain types of data: RDBMS can be less efficient for storing and querying certain types of data, such as hierarchical or multi-structured data.
    
5. Cost: RDBMS can be more expensive to set up and maintain compared to other types of database management systems.
    

## NoSQL Databases

NoSQL stands for "Not Only SQL," and refers to a type of database that does not use the traditional SQL (Structured Query Language) for storing and retrieving data. Instead, NoSQL databases use alternative data models that are optimized for specific types of data and use cases.

Non-relational NoSQL databases do not follow the traditional tabular, row-and-column structure of relational databases. Instead, they use different data models to represent and store data. For example, key-value stores store data as a collection of keys and values, document stores store data as documents, and graph databases store data as a graph of interconnected nodes and edges.

### Types of NoSQL Databases & Comparision

There are several different types of NoSQL databases, each with its own data model and use cases:

| Database | What it is | Use case | Example |
| --- | --- | --- | --- |
| Key-value stores | A simple database that stores data as a collection of keys and values | Fast and efficient storage of simple data | Redis, Amazon DynamoDB |
| Document stores | A database that stores data as documents, typically in JSON or XML format. Document stores are flexible and support complex queries, but may not be as fast as key-value stores. | Storing and querying complex data, such as social media posts or user profiles. | MongoDB, Couchbase |
| Column-oriented databases | A database that stores data in columns rather than rows. This can be more efficient for certain types of data and queries. | Storing and querying large amounts of structured data, such as log data or time series data. | Cassandra, HBase |
| Graph databases | A database that stores data as a graph of interconnected nodes and edges. These databases are optimized for querying and traversing large networks of data. | Storing and querying large networks of data, such as social networks or recommendation systems. | Neo4j, JanusGraph |
| Search engines | A database that stores data as documents and provides powerful search and indexing capabilities. | Efficient search and indexing of large amounts of data, such as a search engine or online retailer's product catalog. | Elasticsearch, Solr |

Use cases for NoSQL databases include situations where the structure of the data is not known in advance, the data is changing rapidly, or the data needs to be distributed across a large number of servers. NoSQL databases are often used in big data and real-time applications, where the performance and scalability of traditional SQL databases may be insufficient. They offer a number of benefits over traditional SQL databases, making them a valuable tool for developers and data professionals.

NoSQL and relational databases are classified based on the way data is stored and accessed.

## Classification of Databases based on architecture and design

Databases are classified into different types based on their architecture and design.

Centralized Database: This type of database has one central database that is accessed by multiple users. It is a single point of control and management for the entire data.

Distributed Database: This type of database is distributed across multiple locations, and can be accessed by multiple users. It allows data to be spread across multiple systems, providing better performance and scalability.

Personal Database: This type of database is intended for use by a single user, and is typically smaller in size. It is used for personal and small-scale data management.

End-User Database: This type of database is designed to be accessed by a specific group of users, such as employees or customers. It is used for specific and restricted data management.

Commercial Database: This type of database is intended for use by businesses and organizations, and typically requires payment to access the data. It is used for commercial and large-scale data management.

Relational Database: This type of database is based on the relational model, which organizes data into one or more tables with relationships between them. It is widely used for transactional systems and large data management.

Cloud Database: This type of database is stored on a remote server and accessed over the internet, usually on cloud infrastructure. It allows data to be accessed from anywhere and is highly scalable.

Object-Oriented Database: This type of database combines the features of an object-oriented programming language with a relational database management system. It allows for the storage of complex data structures, such as object hierarchies, and provides an object-oriented interface for data access and manipulation.


# Conclusion

In this blog post, we have covered the basics of understanding databases and database systems and the differences between NoSQL and RDBMS. We have also discussed the importance of databases in modern technology and the role of backend developers in working with them.

We hope that this post has provided a good introduction to the topic and has given you a better understanding of the benefits and drawbacks of different types of databases. Remember that the choice of database depends on the specific needs of your application and the type of data you are working with.

Thank you for reading this blog post. We would love to hear your thoughts and feedback in the comments section below. Share your knowledge and experiences with databases, and don't hesitate to ask any questions you may have.

As always, happy coding!