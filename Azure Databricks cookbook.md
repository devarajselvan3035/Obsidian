### Aggregation
**UAT** - User Acceptance Testing
**PAT** - Personal Access Token
**ADLS** - Azure Data Lake Storage
**CLI** - Command Line Interface
**ARM** - Azure Resource Manager
### What is UAT
User Acceptance Testing (UAT) is one of the last stages of the software development life cycle. It is performed after the software has been thoroughly tested. It is sometimes known as End User Testing.
### What is ADLS
Azure Data Lake Storage Gen2 (ADLS) is a cloud-based repository for both structured and unstructured data. For example, you could use it to store everything from documents to images to social media streams.
### Azure Databricks offers three environments for building and developing data applications:
• **Databricks Data Science and Engineering**: This provides an interactive workspace that enables collaboration between data engineers, data scientists, machine learning engineers, and business analysts and allows you to build big data pipelines. 
• **Databricks SQL**: This allows you to run ad hoc SQL queries on your data lake and supports multiple visualization types to explore your query results.
• **Databricks Machine Learning**: Provides end-to-end machine learning 
environment for feature development, model training , experiment tracking along with model serving and management.
### what is Data-Bricks job
Orchestrate your data processing, machine learning, or data analytics pipelines on the Databricks platform. You will also start working with Notebooks and scheduling them as Databricks 
jobs.
### Databricks service operates in Azure:
When we create an Azure Databricks service, it operates in the control plane and the data plane:
**Control** **Plane**
* The control plane contains all the services that are managed by Azure Databricks in its own Azure account. All the commands we run will be in the control plane fully encrypted. The customer never resides in the control plane. 
**Data plane**
* The data plane is managed in the customer's Azure account and is where the data resides.
### Databricks Lakehouse
 A data lakehouse is a data management system that combines the benefits of data lakes and data warehouses. A data lakehouse is a new, open data management architecture that combines the flexibility, cost-efficiency, and scale of data lakes with the data management and ACID transactions of data warehouses, enabling business intelligence (BI) and machine learning (ML) on all data.
### Delta Tables
Delta table is **the default data table format in Azure Databricks and is a feature of the Delta Lake open source data framework**. Delta tables are typically used for data lakes, where data is ingested via streaming or in large batches.
### Delta lake
Delta lake enables you to make atomatic changes to a table schema, as well as supports merge, update and delete operations. A Delta Lake is an open-source storage layer designed to run on top of an existing data lake and improve its reliability, security, and performance. Delta Lakes support ACID transactions, scalable metadata, unified streaming, and batch data processing.

**Delta Lake**
A delta lake, an evolution of data storage,  preserves the integrity of your original data without sacrificing the performance and agility required for real-time analytics, artificial intelligence (AI), and machine learning (ML) applications.

**Data Lake**
A data lake is a massive accumulation of raw data in multiple formats. The sheer volume and variety of information in a data lake can make analysis cumbersome and, without auditing or governance, the quality and consistency of the data can be unreliable.

**Data Lakehouse**
A data lakehouse combines the flexibility and scalability of a data lake with the structure and management features of a data warehouse in a simple, open platform. 

**Data Warehouse**
A data warehouse gathers information from multiple sources, then reformats and organizes it into a large, consolidated volume of structured data that’s optimized for analysis and reporting. Proprietary software and an inability to store unstructured data can limit its usefulness.
### Delta lake advantages
* Brings ACID transactions to object storage
* Handle scalable metadata
* Full audit trail of all changes
* Builts upon standard data format: parquet + json
### Advance Features of Delta Lake
**Time Travel**
- Audit data changes
- **DESCRIBE HISTORY** command
   * Returns provenance information, including the operation, user, and so on, for each write to a table. Table history is retained for 30 days
**Query older versions of the data**
► *Using a timestamp*
  ▸ SELECT FROM my_table TIMESTAMP AS OF "2019-01-01"
► *Using a version number* 
  ► SELECT FROM my_table VERSION AS OF 36 
  ► SELECT FROM my_table@v36
**Rollback Versions**
* RESTORE TABLE command:
 * RESTORE TABLE my_table TO TIMESTAMP AS OF "2019-01-01"
 * RESTORE TABLE my_table TO VERSION AS OF 36
**Compaction**
* Compacting Small Files
* OPTIMIZE command:
 * OPTIMIZE my_table
**Indexing**
* Co-locate column information
* OPTIMIZE command:
 * OPTIMIZE my_table ZORDER BY column_name
**Vacuum a Delta table**
* Cleaning up unused data files
  * uncommitted files
  * files that are no longer in in latest table state
* VACUUM command
 * VACUUM table_name [retention period]
 * Default retention period: 7 days
> [!note]
> Note: vacuum = no time travel 

### Relational entities on Databricks
**Tables**
**Manged tables**
* Created under the database directory
 * CREATE TABLE table_name
* Dropping the table, delete the underlying data files
**External tables**
* Created outside the database directo
 * CREATE TABLE table_name LOCATION 'path' 
* Dropping the table, will Not delete the underlying data files
### Hive Metastore
Hive Metastore is a component of Apache Hive, a data warehouse infrastructure built on top of Hadoop. It acts as a central metadata repository that stores and manages metadata information related to tables, partitions, and schemas
### CREATE TABLE vs. CTAS
**CREATE TABLE**
* CREATE TABLE table_1 (coll INT, col2 STRING, col3 DOUBLE)
* Manual schema declaration
* Create empty table
 * Need INSERT INTO statement

**CTAS**
* CREATE TABLE table_1 AS SELECT coll, col2, col3 FROM table_2
* Do Not support manual schema declaration
 * Automatically infer schema
* Table created with data
### Table Constraints
* NOT NULL constraints
* CHECK constraints
* ALTER TABLE table_name ADD CONSTRAINT constraint_name constraint_details
`ALTER TABLE orders ADD CONSTRAINT valid_date CHECK (date > '2020-01-01');`
### Cloning Delta Lake Tables
* Deep Clone
* Shallow Clone
**Deep Cloning**
* Fully copies data + metadata from a source table to a target
* `CREATE TABLE table_clone`
  `DEEP CLONE source_table`
* Can sync changes 
* Take quite a while for large datasets
**Shallow Cloning**
* Quickly create a copy of a table
 * Just copy the Delta transaction logs
* `CREATE TABLE table_clone`
  `SHALLOW CLONE source_table`
### Cloning Delta Lake Tables
* Useful to set up tables for testing in development.
* In either case, data modifications will not affect the source
### views
**Types of views**
* (Stored) Views
* Temp Views
* Global Temp Views

| Views                         | Temp Views                | Global Temp Views              |
| ----------------------------- | ------------------------- | ------------------------------ |
| Persisted in DB               | Session-scoped            | Cluster-scoped                 |
| Dropped only by **DROP VIEW** | Dropped when session ends | Dropped when cluster restarted |
| CREATE VIEW                   | CREATE TEMP VIEW          | CREATE GLOBAL TEMP VIEW        |
### Raw data
**Extract text files as raw strings**
* Text-based files (JSON, CSV, TSV, and TXT formats)
* SELECT * FROM text. /path/to/file`
**Extract files as raw bytes**
* Images or unstructured data
* SELECT * FROM binaryFile./path/to/file
### CTAS: Registering Tables from Files
* CREATE TABLE table_name
 * AS SELECT * FROM file_format.`/path/to/file
* Automatically infer schema information from query results
 * Do Not support manual schema declaration.
 * Useful for external data ingestion with well-defined schema
* Do Not support file options

6382967030

TN36V5514