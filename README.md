# AWS Glue

AWS Glue is a serverless ETL tool.AWS Glue is a fully-managed extract, transform, and load (ETL) service provided by Amazon Web Services (AWS) for processing large amounts of data. It enables users to create and run ETL jobs that extract data from various sources, transform it into the desired format, and load it into target systems for analysis.

AWS Glue offers a visual interface and a code editor for developing ETL jobs using pre-built templates or custom code written in Python or Scala. It also includes a variety of built-in transformations for common data manipulation tasks, such as filtering, mapping, and aggregating data.


# Set Up

1.	Create a bucket
	
	<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230790630-c545c62d-b8d9-4a8e-aaaf-42a33e01f9a0.png">
	
	<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230790719-6571d718-b9a8-4316-9f67-9c034f5e4605.png">
	
	Need to create sub-folders: data,script and temp-dir
	script folder contains the python scripts and temp-dir is use to Glue to process thier jobs releated processings
	
	<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230790883-a356b875-b0f1-4428-9b15-b3424e6c1f12.png">
	
	Need to create three more subfolder inside data folder client_database, client_csv and  dataload=20220329
	
	<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230791496-cba22c21-5a55-4ecb-8d31-5718b79ba97d.png">


2. 	IAM Role for Glue
	Need to create IAM Role and attached the Policy
	
	<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230791961-95a99fed-d4d4-4f73-837f-07255483d996.png">
	
3.	Adding AdminstractorAccess Role is bad for productoin but pratice we can you use 
	
	<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230792083-567d8f51-1334-44d0-861c-a74f4282b7bf.png">
	
	<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230792255-498878bf-08f3-49aa-84b0-7c55b0d44679.png">


# AWS Glue Data Catalog 

The Glue Data Catalog is a fully-managed metadata repository and catalog service provided by Amazon Web Services (AWS) for storing and managing structured and semi-structured data. It serves as a central repository that stores information about data sources, metadata definitions, data lineage, and data transformation processes.


Using Glue Data Catalog, organizations can manage and organize their data assets, and make it easier for data analysts, scientists, and engineers to discover, understand, and use the data. The catalog is designed to work with a range of AWS data services, such as Amazon S3, Amazon RDS, Amazon Redshift, and Amazon Athena, as well as third-party data sources.


# AWS Glue Database

AWS Glue Database is a central metadata repository in AWS Glue that stores information about data sources, targets, ETL jobs, and other artifacts used in the ETL process. It allows users to define and manage tables and schemas that represent their data, making it easier to perform ETL operations and manage data catalogs.


AWS Glue Database provides a logical view of data stored in various sources and enables users to define and organize tables into a hierarchical structure called a database. It supports various data formats, including structured, semi-structured, and unstructured data.

1.	Adding database

<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230836181-8d19ca22-e8f6-4e82-8ac1-e3de63a0c710.png">

2.	Copy of URI from S3 

<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230836649-79d40bdf-2450-44a2-b3a0-c1e020cc60dc.png">

3.	Databse is Created

<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230837000-75949fbf-8642-4f8b-96af-9a75f252d3e2.png">

# AWS Glue Table

An AWS Glue table is a logical representation of a data source that describes the structure and properties of the data. It contains metadata that describes the schema of the data, including column names, data types, and other attributes, and is used by AWS Glue to perform ETL operations on the data.

AWS Glue tables can be created in AWS Glue Database, and users can define the tables using the AWS Glue console or API. When creating a table, users can specify various parameters, such as the data format, location of the data source, and compression type.

AWS Glue tables can be used to transform data during the ETL process, by applying filters, joining data from multiple tables, and performing other data manipulation operations. They can also be used as a target for ETL jobs, where the transformed data is loaded into the table for analysis and querying.

AWS Glue tables support a variety of data formats, including CSV, JSON, Avro, Parquet, and ORC. They also support partitioning, which allows users to organize data into logical partitions based on specific criteria, such as date or region, to improve query performance.

AWS Glue tables are a key component of AWS Glue's ETL capabilities, enabling users to extract, transform, and load data from various sources into a central location for analysis and querying.

# AWS Glue Crawler

AWS Glue Crawler is a service provided by Amazon Web Services (AWS) that automatically discovers and extracts metadata from various data sources, including relational databases, flat files, and semi-structured data. It enables users to create and maintain a data catalog that describes the data available in their environment, making it easier to manage and process large volumes of data.

AWS Glue Crawler works by scanning data sources to infer the schema and structure of the data, and then creates a table definition in the AWS Glue Data Catalog. It can detect changes in the data schema and update the table definition accordingly, ensuring that the catalog remains up-to-date.

AWS Glue Crawler supports a wide range of data sources, including Amazon S3, Amazon RDS, Amazon DynamoDB, and other third-party data stores. It can also detect and handle various data formats, including CSV, JSON, Avro, Parquet, and ORC.

Users can create and manage crawlers using the AWS Glue console or API, and schedule them to run automatically on a regular basis. Crawlers can also be customized to include or exclude specific data sources or tables, and to apply custom data processing logic during the crawl process.

Overall, AWS Glue Crawler simplifies the process of discovering, cataloging, and processing large amounts of data, making it easier for users to perform ETL operations and build data-driven applications.


<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230881148-3c1fb5b7-8d0c-4c75-b6f0-8bb805fb40e9.png">

<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230881263-b79d0f1f-ce29-4c85-90a1-4de8e905a7a3.png">

Added source: Provides the location of S3 from where data need to read

<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230881476-2079275d-36d2-4a03-b930-2cba046cc78f.png">

Attaching the IAM Role

<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230881778-dd67136b-a2b8-4002-b2b3-5622353e5879.png">

Adding the database

<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230881964-897676a8-ec12-4445-ba31-3788d0c15745.png">

<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230882086-7848cb2a-c39e-4269-bffc-488847b0a38b.png">

Crawler Created

<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230882336-54607997-e361-4dca-8b45-b020ec807afd.png">


# Athena

Amazon Athena is a serverless query service that makes it easy to analyze data in Amazon S3 using standard SQL. It allows you to analyze and process vast amounts of data stored in S3 without the need to set up or manage any infrastructure. With Athena, you can run ad-hoc queries to analyze data in S3 and get results in seconds.

Athena is designed to work with structured, semi-structured, and unstructured data stored in S3. You can use it to query data in a variety of formats, including CSV, JSON, ORC, Parquet, and Avro.

Athena is highly scalable and can handle queries that scan terabytes of data. It automatically scales to meet your needs and charges you based on the amount of data scanned by your queries.


<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230884282-046f1d05-0df6-4113-93c2-4680ff8c9864.png">

Location where Anetha process to execute

<img width="588" alt="image" src="https://user-images.githubusercontent.com/64408106/230883062-6ce74cb9-1c57-499e-83c3-fc888b5e4061.png">

# Glue Jobs

AWS Glue Jobs are serverless, which means AWS manages the underlying infrastructure, so you don't need to provision or manage servers. You can create and run ETL jobs in AWS Glue to move and transform data from a variety of sources, such as Amazon S3, relational databases, and data warehouses. AWS Glue Jobs can be written in Python or Scala, and can be scheduled to run on a regular basis or triggered by events.

AWS Glue Jobs also provide built-in support for data quality checks, schema validation, and data transformations. They can be used to perform various types of data processing tasks, such as filtering, aggregating, and joining data. AWS Glue Jobs integrate with other AWS services, such as Amazon Redshift, Amazon Athena, and Amazon EMR, to provide a comprehensive data processing and analysis solution.






















