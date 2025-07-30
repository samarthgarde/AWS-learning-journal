# Relational Databases
AWS RDS is a managed relational database service that simplifies the process of setting up, operating, and scaling a relational database in the cloud.
**important**- We cannot use SSH into our database instances.

# Supported Database Engines

![Supported Engines](images/rds.png)

- **MySQL:** A widely-used open-source relational database management system.
- **PostgreSQL:** An advanced open-source database known for its extensibility and compliance.
- **MariaDB:** A community-developed fork of MySQL, designed for high performance.
- **Oracle:** A robust and feature-rich database management system.
- **Microsoft SQL Server:** A comprehensive enterprise-level database solution from Microsoft.
- **Amazon Aurora:** It provides built-in security, continuous backups, serverless compute, up to 15 read replicas, automated multi-Region replication, and integrations with other AWS services

# Amazon DynamoDB:
DynamoDB is a fully managed and High Available NoSQL Key/Value Database with replications across 3 AZs.
- Scales to massive workloads, distributed “serverless” database (We don't need to manage any server related to this database)
- Millions of requests per seconds, trillions of row, 100s of TB of storage

# Amazon Elastic MapReduce - EMR
EMR stands to Elastic MapReduce and it is a tool to perform big data processing and analysis by provisioning Hadoop Clusters.
- EMR helps us to create Hadoop Clusters (it can be hundreds of EC2 instances) to do big data processing and analysis
- Supports Apache Spark, HBase, Presto, Flink and others.

# Amazon DocumentDB
Amazon DocumentDB is the AWS implementation of MongoDB. It is a NoSQL database and optimized to run in cloud.
- It is used to store, query and index JSON data.

# Steps to Create an RDS Instance:

## Step 1: Log in to AWS Console
First, log in to your AWS Management Console. If you don't have an AWS account, you'll need to sign up for one.

## Step 2: Navigate to RDS
Once you're logged in, navigate to the AWS RDS service. You can find it in the AWS Management Console under the "Database" section.

## Step 3: Choose Database Engine
Click on the "Create Database" button to start the setup process. You'll be prompted to choose a database engine. AWS RDS supports various engines such as MySQL, PostgreSQL, Oracle, SQL Server, and others. Select the engine that fits your application requirements.

## Step 4: Specify Database Details
Next, you'll need to specify details such as DB instance size, storage capacity, and other configuration settings.

## Step 5: Configure Advanced Settings
AWS RDS provides advanced configuration options, including network settings, backup retention periods, and maintenance preferences.

## Step 6: Create Database

## Step 7: Wait for Database to be Available

## Step 8: Configure Security Group

## Step 9: Connect EC2 to RDS

+ Find RDS Endpoint: In the RDS dashboard, locate the endpoint of your RDS instance. This is the hostname you'll use to connect to the database.
+ Install Database Client: On your EC2 instance, install the database client for your chosen database engine. 

```
sudo apt-get update
sudo apt-get install mysql-client
```
+ Connect to RDS: Use the database client to connect to your RDS instance. Replace <endpoint>, <username>, and <password> with your actual RDS endpoint, master username, and password.

```
mysql -h <endpoint> -u <username> -p

```

# Summary

- Relational Databases - OLTP: RDS & Aurora (SQL)
- Differences between Multi-AZ, Read Replicas, Multi-Region
- In-memory Database: ElastiCache
- Key/Value Database: DynamoDB (serverless) & DAX (cache for DynamoDB)
- Warehouse - OLAP: Redshift (SQL)
- Hadoop Cluster: EMR
- Athena: query data on Amazon S3 (serverless & SQL)
- QuickSight: dashboards on your data (serverless)
- DocumentDB: “Aurora for MongoDB” (JSON – NoSQL database)
- Amazon QLDB: Financial Transactions Ledger (immutable journal, cryptographically verifiable)
- Amazon Managed Blockchain: managed HyperLedger Fabric & Ethereum blockchain
- Glue: Managed ETL (Extract Transform Load) and Data Catalog service
- Database Migration: DMS
- Neptune: graph database
