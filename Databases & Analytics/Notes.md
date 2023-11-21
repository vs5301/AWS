Databases 

    Can structure the data, build indexes to efficiently query/search through the data. 
    Define relationships between your datasets

    Databases are optimized for a purpose and come with different features, shapes and contraints

Relational Databases

    Looks like Excel spreadsheets, with links between them
    Can use the SQL language to perform queries/lookups

NoSQL Databases

    Non relational databases
    Purposefuly built for specific data models and have flexible schemas for building modern applications 
    Benefits
        Easy to evolve data model
        Designed to scale-out by using distributed clusters
        Optimized for a specific data model
        Types optimized for the data model

    Examples: Key-value, document, graph, in-memory, search databases

    NoSQL data example: JSON
        JSON = JavaScript Object Notation
        Most common form of data that fits into a NoSQL model
        Data can be nested 
        Fields can change over time
        Support for new types: arrays   

Databases & Shared Responsibility on AWS

    AWS offers use to manage different databases
    Benefits: 
        Quick provisioning, high availability, vertical and horizontal scaling
        Automated backup & restore, operations, upgrades
        Operating system patching is handled by AWS
        Monitoring, alerting

AWS RDS

    Relational Database Service
    Its a managed DB service for DB use SQL as a query language
    It allows you to create databases in the cloud that are managed by AWS
        Postgres
        MySQL
        MariaDB
        Oracle
        Microsoft SQL Server
        Aurora

    Advantages: RDS is a managed service:
        Automated provisioning, OS patching
        Continuos backups and restore to specific timestamp
        Monitoring dashboards
        Read replicas for improved read performance 
        Multi AZ setup for disaster recovery
        Maintenance windows for upgrades
        Scaling capability (vertical and horizontal)
        Storage backed by EBS (gp2 or io I)

    Cannot SSH into you instances

Amazon Aurora

    Proprietary technology from AWS
    PostgreSQL and MySQL both supported as Aurora DB
    AWS cloud optimized and claims 5x performance improvement over MySQL on RDS, over 3x the performance of Postgres on RDS
    Aurora storage automatically grows in increments of 10GB
    Aurora costs more than RDS (20%) - but is more efficient
    Not in free tier

Amazon Aurora Serverless

    Automated database instantiation and auto-scaling based on actual usage
    PostgreSQL and MySQL are both supported as Aurora Servereless DB
    No capacity planning needed
    Lease management overhead
    Pay per second, can be more cost-effective
    Use cases: good for infrequent, intermittent or unpredictable workloads

    Aurora with no management overhead - Aurora Serverless

RDS Deployments

    Read Replicas:
        Scale the read workload of your DB
        Can create up to 15
        Data is only written to the main DB

    Multi-AZ:
        Failover in case of AZ outage (high availability)
        Data is only read/written to the main database

    Multi Region (Read Replicas)
        Disaster recovery in case of region issue
        Local performance for global reads
        Replication cost
    
Amazon ElastiCache

    The same way RDS is to get managed Relational Databases
    ElastiCache is to get managed Redis or Memcached
    Caches are in-memory databases with high performance, low latency
    Helps reduce load off databases for read intensive workloads

    AWS takes care of OS maintenance/patching, optimizations, setup, configuration, monitoring, failure recovery and backups.

DynamoDB

    Fully managed highly available with replication across 3 AZ
    NoSQL database - not a relational database
    Scales to massive workloads, distributed "serverless" database
    Millions of requests per seconds, trillions of row, 100s of TB of storage
    Fast and consistent in performance
    Single-digit millisecond latency - low latency retrieval
    Integrated with IAM for security, authorization and adminintration
    Low cost and auto scaling capabilities 
    Standard & infrequent Access (IA) Table class

    Key/value database

DynamoDB Accelerator - DAX

    Fully managed in-memory cache for DynamoDB
    10x performance improvement -single-digit millisecond latency to microseconds latency - when accessing your DynamoDB tables
    Secure, highly scalable & highly available
    Differeence with ElastiCache at the CCP level: DAX is only used for and is integrated with DynamoDB, while ElastiCache can be used for other databases

DynamoDB - Global Tables

    Make a DynamoDB table accessible with low latency in multiple-regions
    Active-active replication (read/write to any AWS region)

Redshift

    Based on PostgreSQL, but it's not used for OLTP
    It's OLAP - online analytical processing (analytics and data warehousing)
    Load data once every hour, not every second
    10x better performance than other data warehouses, scales to PBs of data
    Columnar storage of data (instead of row based)
    Massively Parallel Query Execution (MPP), highly available
    Pay as you go based on the instances provisioned
    Has aSQL interface for performing the queries
    BI tools such as AWS Quicksight or Tableau integrate with it

Redshit Serverless

    Automatically provisions and scales data warehouse underlying capacity
    Run analytics workloads without managing data warehouse infrastructure
    Pay only for what you use (save costs)
    Use cases: Reporting, dashboarding applications, real-time analytics

Amazon EMR - Elastic Map Reduce

    Helps creating Hadoop clusters (Big Data) to analyse and process vast amount of data
    The clusters can be made of hundreds of EC2 instances
    Also supports Apache Spark, HBase, Presto, Flink
    EMR takes care of all the provisioning and configuration
    Auto-scaling and integrated with Spot instances
    Use cases: data processing, machine learning, web indexing, big data

Amazon Athena

    Serverless query service to perform analytics against S3 objects
    Uses standard SQL language to query the files
    Supports CSV, JSON, ORC, Avro and Parquet
    Pricing $5.00 per TB of data scanned
    Use compressed or columnar data for cost-savings (less scan)
    Use cases: Business intelligence/analytics/reporting, analyse & query VPC Flow Logs, ELB Logs, CloudTrail trails, etc

    Analyse data in S3 using serverless SQL, use Athena


Amazon QuickSight

    Serverless machine learning-powered business intelligence service   to create interactive dashboards
    Fast, automatically scalable, embeddable, with per-session pricing
    Use cases:
        Business analytics
        Building visualizations
        Perform ad-hoc analyics
        Get business insights using data

    Integrated with RDS, Aurora, Athena, Redshift, S3, etc

DocumentDB

    Document is a no-SQL database
    Fully managed, highly available with replication across 3 AZ
    DocumentDB storage automatically grows in increments of 10GB, upto 64TB
    
    Automatically scales to workloads with millions of requests per second

Amazon Neptune

    Fully managed graph database
    Eg of graph database - social network
    Highly available across 3 AZ, with up to 15 read replicas
    Exam - Anything related to graph database - Amazon Neptune

Amazon QLDB - Quantum Ledger Database

    Fully managed, serverless, highly available, replication across 3 AZ
    Used to review history of all the changes made to your application data over time
    Immutable system: no entry can be removed or modified, cryptographically verfiable
    Exam - Anything related to financial transactions and ledgers - QLDB

Amazon Managed Blockchain

    Managed service to 
        Join public blockchain networks 
        Or create your own scalable private network

    Exam - Anything related to blockchains, hyperledger fabric or ethereum - Amazon managed Blockchain - decentralized blockchain

AWS Glue

    Managed extract, transform and load (ETL) service
    Useful to prepare and transform data for analytics
    Fully serverless service

Database Migration Service - DMS

    Quickly and securely migrated databases to AWS, resilient, self healing
    Source database remaining available during migration
    Supports homogeneous, eg: Oracle to Oracle and heterogeneous migrations, eg: SQL server to Aurora

    Exam - Anything related to migration of database - DMS