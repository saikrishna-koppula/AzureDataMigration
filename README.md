## Azure Data Migration Project Overview

This is an end-to-end data engineering project I am working on, involving:

1. **Creating my own POS database by hosting an On-Premises SQL Server for Transactional Processing by:**
   - Structuring the database according to the needs of transactional processing
   - Normalizing the database
   - Storing data efficiently

2. **Setting up the cloud stack for an analytical database by:**
   - Creating the resource group on Azure Cloud
   - Provisioning Azure Data Lake Storage, Azure Databricks, and other required tools

3. **Migrating the on-premises SQL Server database to Azure Cloud for Analytical Processing by:**
   - Creating a data pipeline for moving historical data as a one-time data migration using Azure Data Factory
   - Setting up a data pipeline to automate data transfer from SQL Server to Azure Data Lake using a delta data load process
   - Using Azure Databricks to transform raw data into an analytical dataset
   - Creating an Azure Synapse Analytics SQL Database to query data in the data lake for reporting needs

4. **Creating reports on the analytical database by:**
   - Designing Tableau dashboards to visualize key metrics and display insights from the analytical database

## Pipeline Architecture & Data Lineage Diagram
![Data Lineage Architecture Image](./img/Azure%20data%20lineage.png)