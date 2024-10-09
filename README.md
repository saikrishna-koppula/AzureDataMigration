# Azure Data Migration Project
This is an end-to-end data engineering project involving:
- Development of a structure for a POS database on an On-Premises SQL Server for OLTP
- Migration of the on-premises SQL Server database to Azure Cloud to enable OLAP
  - Data Pipeline creation for moving historical data as a one time data migrations using Azure Data Factory
  - Data Pipeline creation to automate data transfer from SQL Server to Azure Data Lake using delta data load process
  - Usage of Azure Databricks to transform raw data into analytical dataset
  - Creation of Azure Synapse Analytics SQL Database to query data in data lake for reporting needs
  - Creation of Tableau dashboards to visualize key metrics and display insights
 
    
