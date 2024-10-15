# Azure Data Pipeline for Sales Order Processing

## Overview
This project implements an automated data pipeline using Azure services to process sales order data. The pipeline ingests CSV files from Amazon S3, validates the data, and routes it to appropriate storage locations in Azure Data Lake Storage Gen2 based on predefined criteria. It also includes data processing and loading into an Azure SQL Database for reporting purposes.

## Architecture
[Insert your architecture diagram here]

## Azure Services Used
- Azure Data Lake Storage Gen2 (ADLS Gen2)
- Azure Blob Storage
- Azure Data Factory
- Azure Databricks
- Azure Key Vault
- Azure SQL Database

## Key Features
- Automated file ingestion from Amazon S3 to ADLS Gen2
- Data validation and processing using Azure Databricks
- Dynamic handling of valid order statuses stored in Azure SQL Database
- Secure storage of sensitive information using Azure Key Vault
- Data segregation into high-value, low-value, and erroneous orders
- Automated pipeline triggering using Storage Event triggers

## Implementation Steps

### 1. Resource Creation
- Create a Resource Group in Azure
- Create a normal Blob Storage Account
- Create ADLS Gen2 Storage Account (with hierarchical namespace enabled)
- Create an Amazon S3 bucket and upload order_items.csv
- Create an Azure Data Factory
- Create an Azure Databricks workspace
- Create an Azure Key Vault
- Create an Azure SQL Database and Server

### 2. Data Factory Configuration
- Create Linked Services for:
  - Amazon S3
  - ADLS Gen2
  - Azure Databricks
  - Azure Key Vault
  - Azure SQL Database
- Create Datasets for source and sink data
- Implement pipelines for data ingestion, processing, and SQL database population

### 3. Data Processing
- Implement data flow in Azure Data Factory to:
  - Segregate data into high-value, low-value, and erroneous orders
  - Perform necessary data transformations
- Create output folders in ADLS Gen2 for processed data

### 4. SQL Database Setup
- Create and populate valid_order_status table
- Create table definition for premium orders (high-value orders)

### 5. Pipeline Organization
- Organize datasets and pipelines into logical folders
- Implement pipeline chaining using Execute Pipeline activity

### 6. Trigger Setup
- Create a Storage Event trigger to automate pipeline execution on file arrival

## Getting Started
[Add instructions on how to set up and run the project]

## Prerequisites
- Azure subscription
- AWS account with S3 access
- Necessary permissions for creating and managing Azure resources

## Future Enhancements
- Implement real-time monitoring and alerting
- Extend pipeline to handle multiple file types
- Add advanced data quality checks and reporting

[Add any additional sections relevant to your specific implementation]
