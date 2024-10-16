## Hive Tutorial for Beginners | Hive Architecture | Hadoop Hive Tutorial | Hadoop Training | Edureka

## Introduction

In chapter 1 of the article, the focus is on introducing Apache Hive as an open-source software utility with a SQL-like interface used for data querying and analytics. The chapter encourages viewers to subscribe to the Edureka YouTube channel for updates on trending IT technologies and offers a link for online certification and training in Hadoop and big data.

## Agenda

Chapter 2 of the article delves into the importance of Apache Hive within the context of Hadoop, discussing its features, architecture, components, installation process on Windows OS, data types, operators, data models, and concludes with a brief demo of Apache Hive.

## Why Hive

Chapter 3 discusses the need for Apache Hive in handling large amounts of data, particularly in the context of Facebook's massive user base and data volume. It highlights the limitations of traditional DBMS in processing such vast amounts of data and introduces Hadoop as a solution. The chapter also explains how Apache Hive was developed to provide a SQL-like interface for querying big data stored in Hadoop.

## Definition of Hive

Chapter 4 explains the definition and features of Apache Hive, emphasizing its role as a data warehouse project on top of Apache Hadoop. It highlights Hive's SQL-like interface for querying and analyzing data stored in different databases and file systems that integrate with Hadoop. Additionally, it mentions Hive's utility for data analytics, simplifying data querying for structured data without the need to learn Java or Hadoop API.

## Hive Applications

Chapter 5 discusses various important applications of Apache Hive, including 
* data warehousing, 
* document indexing, 
* predictive modeling, 
* business intelligence, 
* and log processing. 
Hive is used in major applications such as data summarization, query analysis, and data indexing to improve query performance and enable ad hoc queries against large datasets. It is a versatile tool that helps companies predict business requirements accurately and process data efficiently with SQL-like queries.

## Hive Features

Chapter 6 of the article discusses the key features of Apache Hive, including its support for SQL-like queries, online analytical processing (OLAP), speed, scalability, extensibility, and ad-hoc querying capabilities. Hive's SQL-like interface makes it easy for Hadoop developers to write queries, while its OLAP design allows for analyzing data from multiple database systems simultaneously. Additionally, Hive is known for its speed, scalability, and extensibility, as it directly defines tables in the Hadoop file system. Lastly, Hive enables ad-hoc querying for data analysis and prediction.

## Hive Architecture

Chapter 7 of the article delves into the Apache Hive architecture, detailing the flow of query submission. It begins with the Hive client, which supports various programming languages and client types such as Thrift server, JDBC driver, and ODBC driver. The architecture also includes Hive services like Hive CLI, Hive web UI, and Hive metastore, as well as the Hive execution engine, which optimizes and executes tasks in the order of their dependencies using MapReduce and HDFS. The HDFS serves as the storage location for the data processed by Hive.

## Hive Components

Chapter 8 of the article discusses the different components of Apache Hive, including the shell for writing and executing queries, the metastore for storing table details, the execution engine for converting queries into a language Hive can understand, the driver for executing code in cyclic graphs, and the compiler for compiling and providing output. The chapter also covers the installation of Apache Hive on a Windows operating system using Oracle VirtualBox and Cloudera QuickStart VM. The default username and password for Cloudera are both 'cloudera'.

## Data Types

Chapter 9 of the article discusses various data types in Apache Hive, which are similar to those found in other programming languages. These include 
**Integer**
* tiny, 
* small, 
* integer, 
* big 
**Float**
* float, 
* double, 
**Character**
* string 
* boolean data types. 
These data types are commonly used in programming and are essential for working with data in Hive.

## Hive Data Models

Chapter 10 of the article discusses Hive data models, including 
* databases, 
* tables, 
* partitions, and 
* buckets. 
It explains how these data models are used to store and organize data in Hive, making it easier to query and access specific information. The chapter also introduces operators, such as arithmetic and logical operators, which are commonly used in programming languages and can be applied to data stored in Hive tables.

### CSV Files

Chapter 11 of the article discusses the CSV files used in the demo, which were created using MS Excel and saved as .CSV files. The files include employee data with columns for employee ID, name, salary, age, and country. The smaller size of the CSV files helps reduce execution time when working with Cloudera.

### Demo

Chapter 12 of the article introduces additional CSV files, including one for departments and another for student reports. The chapter also provides instructions on how to start Hive in a terminal and create a database for the demo. The article includes a document with all the necessary codes for executing the demo, which can be accessed in the description box for practice.

### Create Database

Chapter 13 of the article discusses creating a database using SQL commands, checking if the database has been successfully created, and creating tables in Hive. It explains the difference between managed/internal tables and external tables, highlighting the importance of using external tables to ensure data security in case of accidental deletion.

### Create Internal Table

Chapter 14 discusses creating an internal table in Hive using SQL commands. The code provided demonstrates creating a table named "employee" with columns for ID, name, salary, and age. The table is created successfully, and the chapter also covers describing the table to view its structure.

### Describe Table

Chapter 15 continues by discussing how to describe a table in Hive using SQL commands and differentiate between internal, managed, and external tables. The chapter demonstrates creating an external table by adding the keyword "external" to the SQL command. It also covers specifying a location for the external table and uploading a data file into Hive. Additionally, the chapter briefly touches on editing tables and making alterations to the table structure.

### Alter Table

Chapter 16 of the article discusses how to rename a table in Hive using the ALTER command, as well as how to add new columns to an existing table. The chapter demonstrates changing the name of a column from "name" to "first name" and successfully adding a new column named "surname" to the table. It also covers how to describe the table to confirm the changes made.

### Partition

Chapter 17 of the article focuses on partitioning as a data model in Hive. It compares partitioning to organizing students in a college by their respective departments, making it easier to locate specific individuals. The chapter explains how to create a new database for partitioning, switch to using that database, and create a table within it. It emphasizes the simplicity and efficiency of partitioning for executing queries.

### Partition Table

Chapter 18 discusses partitioning a table based on a specific column, in this case, the course column. The chapter explains how to partition the table using the course column and provides a code example for partitioning students based on their courses. The chapter concludes with a demonstration of the partitioning execution and checking the columns present in the table.

### Partition Table Based on Course

Chapter 19 discusses dynamic partitioning in Hive, where the values of partitioned columns exist within the table and do not need to be passed manually. The chapter explains the difference between dynamic and static partitioning, provides code examples for dynamic partitioning, and demonstrates how to set up dynamic partitioning in Hive. It also covers setting the partition mode to non-strict and loading data into a table using dynamic partitioning.

### Partition based on Course

Chapter 20 continues the discussion on dynamic partitioning in Hive, focusing on partitioning the table based on the course column. The chapter demonstrates how to load data into the partitioned table using code, which automatically segregates students based on their courses (Hadoop, Java, Python). The process involves executing MapReduce jobs to separate and load the data into different files based on the course. The chapter emphasizes the importance of hands-on experience with real-time data to enhance skills and increase job placement opportunities.

### Bucketing

Chapter 21 delves into the concept of bucketing in Hive, the last type of data model discussed in the tutorial. The chapter covers creating a new database and table, loading data, enabling bucketing, clustering data based on ID into three buckets, and overwriting the table with the clustered data. The process involves executing MapReduce jobs to categorize the data into buckets, ultimately demonstrating the successful insertion of data into the buckets. The chapter concludes with a manual refresh to verify the completion of the bucketing process.

### Basic Operations

Chapter 22 focuses on the basic operations that can be performed in Hive. The chapter begins by creating a new database specifically for Hive query language operations. The author emphasizes the importance of organizing and sorting data in a structured manner for better clarity and understanding. The chapter sets the stage for discussing various operations that can be executed in Hive, highlighting the significance of creating separate databases for different functionalities.

### Adding Data

Chapter 23 delves into practical examples of basic operations in Hive, such as adding and subtracting values from a column, as well as performing logical operations to filter data based on specific criteria. The chapter demonstrates how to manipulate data within a table using mathematical and logical operations, showcasing the versatility and functionality of Hive in processing and analyzing data.

### Creating Table

Chapter 24 demonstrates the process of creating a table in a specific database, loading data into the table, and applying functions to manipulate the data. The chapter showcases examples of applying functions such as finding the square root of salaries and determining the maximum salary in the dataset. The chapter also mentions the execution speed may vary based on system configuration.

### Minimum Salary

Chapter 25 demonstrates additional operations that can be performed on the data, such as finding the minimum salary and identifying the employee with that salary. The chapter also showcases examples of converting employee names to uppercase and lowercase using functions in Hive. These operations help in manipulating and transforming the data as needed.

### Group by Function

Chapter 26 focuses on utilizing the group by function in Hive to categorize employees based on their countries. The chapter demonstrates creating a separate database named "group" and creating a table within it. Data is then loaded into the table from a new CSV file, which includes an additional column for country. The chapter emphasizes the importance of hands-on learning and understanding the advantages and disadvantages of technology through practical application.

### Error

Chapter 27 discusses correcting an error in table creation by dropping the incorrect table and creating a new one named "employ group." Data is then added to the new table, and the group by function is used to categorize employees based on their countries. The chapter demonstrates executing MapReduce jobs to categorize employees by country and calculate the sum of their salaries. Additionally, a command using group by function to categorize employees based on country and salary sum greater than or equal to 15,000 is also executed.

### Order by

Chapter 28 covers the execution of the data card to obtain the desired output. The chapter then delves into understanding the "order by" and "sort by" methods by creating a new database named "orders" and utilizing it for further exploration.

### Load Data

Chapter 29 focuses on creating a new table named "employ_order" and loading data into it. The data is then ordered based on descending order of salary, showcasing the highest and lowest salaries. The chapter also introduces the "sort by" command and discusses various operations and functions that can be performed in Hive, including joins. A new table named "EMPDept" is created for join operations, along with loading data into it.

### Inner Join

Chapter 30 discusses the process of performing different types of joins in Hive, including inner join. The chapter demonstrates how to select employee names and departments based on employee and department IDs, and shows the successful completion of MapReduce tasks. It also mentions the availability of other join types such as left outer join, right outer join, and full outer join in Hive.

### Left Outer Join

Chapter 31 continues to demonstrate different types of joins in Hive, specifically focusing on left outer join and right outer join. The chapter shows how to use the keywords "left outer join" and "right outer join" in Hive commands to perform these types of joins, with successful execution of MapReduce jobs and generation of output.

### Full Outer Join

Chapter 32 demonstrates the execution of a full outer join in Hive by using the keyword "full outer join" in the command. The chapter shows the successful execution of the full outer join operation, generating the desired output.

### Summary

Chapter 33 discusses the limitations of Apache Hive, highlighting that it is not suitable for handling real-time data processing and online transaction processing due to its batch processing nature. The chapter also mentions that Hive queries have high latency, taking longer to process compared to real-time tools like Spark and Kafka. Additionally, the chapter concludes by encouraging viewers to reach out with any queries or for access to the code used in the tutorial.