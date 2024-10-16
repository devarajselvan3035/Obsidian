## Airflow Tutorial for Beginners - Full Course in 2 Hours 2022

### Airflow Introduction

Chapter 1 of the Airflow Tutorial for Beginners Full Course introduces the course and encourages beginners to follow hands-on examples to learn about Apache Airflow, task lifecycle, basic architecture, building airflow dags with different operators, sharing data between tasks, and connecting to external services like Postgres DB and AWS S3. The chapter also covers new features introduced in Airflow 2.0 and ends with tips on installing python packages in the airflow docker container.

### Run Airflow in Python Env

Chapter 2 of the Airflow Tutorial for Beginners Full Course covers setting up a Python environment, installing Apache Airflow locally, initializing the database, starting the Airflow webserver, creating a user, starting the scheduler, and running example DAGs successfully. The chapter also introduces Docker as a platform for software delivery and environment isolation.

### Run Airflow in Docker

Chapter 3 of the Airflow Tutorial for Beginners Full Course covers setting up Apache Airflow with Docker. The chapter guides you through installing Docker and Docker Compose, downloading the official Docker Compose YAML file, modifying the file to use LocalExecutor, creating necessary folders, initializing the database, and running Airflow in Docker. By following the steps outlined in the chapter, you can successfully set up and run Airflow in a Docker environment.

### Airflow Basics and Core Concepts

Chapter 4 of the Airflow Tutorial for Beginners Full Course explains the origins of Apache Airflow as an internal tool at Airbnb in 2014, which later became an open-source project under the Apache Software Foundation. It introduces the concept of workflows as directed acyclic graphs (DAGs) consisting of tasks and operators. Tasks represent units of work within a DAG, while operators determine the specific actions to be executed by each task. The chapter also discusses the execution date, DAG run, and task instance within the context of Airflow's workflow management platform.

### Airflow Task Lifecycle

Chapter 5 of the Airflow Tutorial for Beginners Full Course explains the task life cycle in Apache Airflow. Tasks in a DAG run go through different stages such as queued, running, success, failed, and shutdown. The chapter details the 11 different stages a task can go through, including how tasks are scheduled, executed, retried, and rescheduled based on their status. The goal is to achieve a successful workflow execution process starting from no status to task completion.

### Airflow Basic Architecture

Chapter 6 of the Airflow Tutorial for Beginners Full Course delves into the basic architecture of Apache Airflow. It explains the various components such as the data engineer, web server, scheduler, worker, and DAG, and their responsibilities in the workflow process. The data engineer plays a crucial role in configuring the Airflow setup, creating and managing DAGs, and monitoring ETL processes. The components work together to update and retrieve information from the database, with options for different database engines like MySQL and Postgres. The chapter also demonstrates how to launch Airflow using Docker Compose in VSCode.

### Airflow DAG with Bash Operator

Chapter 7 of the Airflow Tutorial for Beginners Full Course focuses on setting up Airflow in a local environment and creating a custom DAG. It covers steps such as removing example DAGs, initializing Airflow, defining a DAG with parameters like start date and schedule interval, creating tasks using operators like BashOperator, and setting task dependencies. The chapter also explores different methods for defining task dependencies and demonstrates how to view and manage DAGs and task executions in the Airflow UI.

### Airflow DAG with Python Operator

Chapter 8 of the Airflow Tutorial for Beginners Full Course delves into creating a custom DAG using PythonOperator in Airflow. It covers steps such as defining default arguments, setting up the DAG with a start date and schedule, creating a Python function to run as a task, using PythonOperator to execute the function, passing parameters to the function, and sharing information between different tasks. The chapter demonstrates how to trigger the DAG, check task logs, and successfully pass parameter values to the Python function.

### Data Sharing via Airflow XComs

Chapter 9 of the Airflow Tutorial for Beginners Full Course focuses on using Airflow Xcoms to push and pull information between tasks. By default, every function's return value is automatically pushed into Xcom. The chapter demonstrates how to push and pull values using Xcoms, distinguish between multiple values pushed into Xcoms, and shares a caution about the maximum size limit of Xcoms being 48 KB. The chapter also covers updating code to get age via Xcoms instead of op_kwargs and emphasizes the importance of not using Xcoms for sharing large data to avoid crashing.

### Airflow Task Flow API

Chapter 10 of the Airflow Tutorial for Beginners Full Course focuses on rewriting a DAG using the TaskFlow API to reduce the amount of code needed. The chapter demonstrates how to create a new Python file, define tasks using Python functions with decorators, set dependencies between tasks, and handle multiple outputs using Xcoms. By utilizing the TaskFlow API, the DAG can be implemented with around 40 lines of code, significantly reducing the code complexity compared to using the PythonOperator.

### Airflow Catch-Up and Backfill

Chapter 11 of the Airflow Tutorial for Beginners Full Course focuses on implementing catchup and backfill features in a DAG. The chapter demonstrates how to set the catchup parameter to True to run the DAG since the start date, and then how to disable catchup and use the backfill command to manually run DAG runs in the past. The process involves updating the DAG version, executing the backfill command in the Airflow scheduler container, and verifying the results in the browser.

### Airflow Scheduler with Cron Expression

Chapter 12 of the Airflow Tutorial for Beginners Full Course focuses on creating a DAG with a customized schedule using cron expressions. The chapter explains how to define a DAG with a specific schedule_interval parameter, either using Airflow cron presets or custom cron expressions. It demonstrates how to use crontab.guru to generate and verify cron expressions for scheduling tasks at specific times and days. The chapter also shows how to run a DAG weekly on multiple weekdays by adding commas or specifying a range of days in the cron expression.

### Airflow Connection to Postgres

Chapter 13 of the Airflow Tutorial for Beginners Full Course explains the importance of using Airflow Connections to connect to external services such as database servers and cloud servers. It demonstrates how to create and manage connections in the Airflow web server UI, including defining the name of the connection and necessary credentials. The chapter also introduces how to use connections with the PostgresOperator in Airflow.

### Airflow Postgres Operator

Chapter 14 of the Airflow Tutorial for Beginners Full Course focuses on demonstrating the use of the PostgresOperator in Airflow by connecting to a Postgres database and creating tables. It covers setting up connections, creating tasks with the PostgresOperator, troubleshooting errors, and inserting data into the database. The chapter also emphasizes the importance of deleting data before inserting to avoid duplication or primary key violations. It provides a step-by-step guide on how to create tasks, manage dependencies, and verify data insertion using DBeaver.

### Airflow Docker Install Python Package 2 ways

Chapter 15 of the Airflow Tutorial for Beginners Full Course discusses the options of extending or customizing the Airflow Docker image to install Python dependencies. Extending the image is quick and easy, while customizing allows for more control over the image size and optimization. The chapter provides a detailed guide on how to extend the Airflow image by adding Python dependencies, building the image, and verifying the installation. It also explains the process of customizing the Airflow image by building it from the source code and installing dependencies. The chapter concludes by suggesting that extending the image is suitable for most cases, but customizing may be necessary for specific customization and optimization needs.

### Airflow AWS S3 Sensor Operator

Chapter 16 of the Airflow Tutorial for Beginners Full Course focuses on using sensors in Airflow to wait for specific events, such as the existence of a file in an S3 bucket. The chapter provides a step-by-step guide on setting up a MinIO S3 bucket, creating a DAG to sense the file's existence, and configuring the S3KeySensor operator to monitor the bucket. It also covers setting up an AWS S3 connection, troubleshooting task failures, and adjusting poke intervals and timeouts for the sensor task. The chapter concludes with a demonstration of the sensor task successfully detecting the file's presence in the bucket.

### Airflow Hooks S3 PostgreSQL

Chapter 17 of the Airflow Tutorial for Beginners Full Course focuses on importing a CSV file called orders into a Postgres database, writing a DAG to query data from the database, and uploading it to an S3 bucket. The chapter covers creating a table in the Postgres database, querying data using the Postgres operator, and uploading the data to the S3 bucket using the S3 hook library. It also demonstrates how to dynamically name text files and upload them to the S3 bucket, ensuring workspace cleanliness by using the tempfile package to create temporary files.

### Course Bonus

Chapter 18 of the Airflow Tutorial for Beginners Full Course concludes the course by congratulating the viewer on completing it and encouraging them to subscribe, like, and turn on notifications for future videos. The chapter also mentions the possibility of creating a new Airflow Tutorial video based on achieving a certain number of likes. The viewer is thanked for watching and told that they will talk to them in the next video.