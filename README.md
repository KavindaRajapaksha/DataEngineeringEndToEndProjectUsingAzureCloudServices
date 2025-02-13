# Azure End-to-End Data Engineering Real-Time Project

This project is a data engineering pipeline solution designed to address a business problem while enhancing my learning and understanding of data pipelining.

## Project Overview

This project focuses on building a comprehensive data pipeline on Azure to extract customer and sales data from an on-premises SQL database, transform it in the cloud, and generate actionable insights through a Power BI dashboard. The dashboard will display key performance indicators (KPIs) related to gender distribution and product category sales, allowing stakeholders to filter and analyze data based on date, product category, and gender.

## Business Requirements

The business needs better insights into customer demographics—particularly gender distribution—and how it influences product purchases. The key requirements include:

- **Sales by Gender and Product Category**: A dashboard showing the total products sold, total sales revenue, and gender distribution among customers.
- **Data Filtering**: Ability to filter the data by product category, gender, and date.
- **User-Friendly Interface**: Stakeholders should have an intuitive interface for querying data.

## Solution Overview

To meet these requirements, the solution consists of the following components:

### Data Ingestion
- Extract customer and sales data from an on-premises SQL database.
- Load the data into Azure Data Lake Storage (ADLS) using Azure Data Factory (ADF).

### Data Transformation
- Use Azure Databricks to clean and transform the data.
- Organize the data into **Bronze, Silver, and Gold** layers for raw, cleansed, and aggregated data.

### Data Loading and Reporting
- Load the transformed data into **Azure Synapse Analytics**.
- Build a **Power BI** dashboard to visualize the data and provide insights into sales and customer demographics.

### Automation
- Schedule the pipeline to run daily, ensuring up-to-date data and reports.

## Technology Stack
- **Azure Data Factory (ADF)**: Orchestrates data movement and transformation.
- **Azure Data Lake Storage (ADLS)**: Stores raw and processed data.
- **Azure Databricks**: Performs data transformation and processing.
- **Azure Synapse Analytics**: Provides data warehousing and SQL-based analytics.
- **Power BI**: Used for data visualization and reporting.
- **Azure Key Vault**: Securely manages credentials and secrets.
- **SQL Server (On-Premises)**: Source of customer and sales data.

## Setup Instructions

### Prerequisites
- An **Azure account** with sufficient credits.
- Access to an **on-premises SQL Server database**.

### Step 1: Azure Environment Setup
1. **Create a Resource Group**: Set up a new resource group in Azure.
2. **Provision Services**:
   - Create an **Azure Data Factory** instance.
   - Set up **Azure Data Lake Storage** with Bronze, Silver, and Gold containers.
   - Set up an **Azure Databricks workspace** and an **Azure Synapse Analytics workspace**.
   - Configure **Azure Key Vault** for secret management.

### Step 2: Data Ingestion
1. **Set up SQL Server**: Install SQL Server and SQL Server Management Studio (SSMS). Restore the AdventureWorks database.
2. **Ingest Data with ADF**: Create pipelines in ADF to copy data from SQL Server to the **Bronze layer** in ADLS.

### Step 3: Data Transformation
1. **Mount Data Lake in Databricks**: Configure Databricks to access ADLS.
2. **Transform Data**: Use Databricks notebooks to clean and aggregate the data, moving it from Bronze to Silver and then to Gold.

### Step 4: Data Loading and Reporting
1. **Load Data into Synapse**: Set up a Synapse SQL pool and load the **Gold** data for analysis.
2. **Create Power BI Dashboard**: Connect Power BI to Synapse and create visualizations based on business requirements.

### Step 5: Automation and Monitoring
1. **Schedule Pipelines**: Use ADF to schedule the data pipelines to run daily.
2. **Monitor Pipeline Runs**: Utilize monitoring tools in ADF and Synapse to ensure successful pipeline execution.

### Step 6: Security and Governance
1. **Manage Access**: Implement role-based access control (RBAC) using **Azure Entra ID (formerly Active Directory)**.
2. **Encrypt Data**: Use **Azure Key Vault** to securely store credentials and encryption keys.

### Step 7: End-to-End Testing
1. **Trigger and Test Pipelines**: Insert new records into the SQL database and verify that the pipeline updates the Power BI dashboard successfully.

## Conclusion
This project provides an end-to-end data engineering solution that helps stakeholders understand customer demographics and their impact on sales. The automated data pipeline ensures access to the most current and actionable insights, making data-driven decision-making more effective.
