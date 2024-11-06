# Azure Data Migration Project Overview

This is an end-to-end data engineering project involving:

1. Creating your own POS database by hosting an On-Premises SQL Server for Transactional Processing.
   - Structuring your database according to the needs of transational processing
   - Normalizing your database
   - Storing data efficiently
2. Setting up your cloud stack for an analytical database
   - Creating your resource group on Azure Cloud
   - Provisioning Azure Data Lake Storage, Azure Data Bricks and other required tools
3. Migrating the on-premises SQL Server database to Azure Cloud to enable Analytical Processing.
   - Data Pipeline creation for moving historical data as a one time data migrations using Azure Data Factory
   - Data Pipeline creation to automate data transfer from SQL Server to Azure Data Lake using delta data load process
   - Usage of Azure Databricks to transform raw data into analytical dataset
   - Creation of Azure Synapse Analytics SQL Database to query data in data lake for reporting needs
4. Creating reports on the analytical database
   - Creation of Tableau dashboards to visualize key metrics and display insights from the analytical database

# Pipeline Architecture & Data Lineage Diagram
![Data Lineage Architecture Image]