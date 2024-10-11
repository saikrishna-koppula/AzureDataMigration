# Project Setup
## On-premises SQL Server Setup
1. Download and Install SQL Server on a system that will act as your On-Premises hardware.
2. Download SQL Server Management Studio (SSMS) and use it to host a local SQL server.
3. Create a user in the database and grant required premissions so that it can be used to log into the database when being accessed from cloud. 
4. Create the tables as per your data structure and load data into the tables.

### Loading data into the on premises SQL Server
1. 



Now that your on premise database is ready, let us start creating our cloud database which will be the source for OLAP.

## Azure Cloud Setup
1. Create a resource group for the project: rg-db-migration-project
2. Create the following services under the resource group: Azure Databricks Service, Data Factory (V2), Synapse Workspace, Key Vault, and a Data Lake storage account. <Image>
3. Add the SQL Server database user credentials (created in the On-premises SQL Server Setup step) to Key Vault.
4. Navigate to data lake resource and create the following containers under Data Storage:
   - Source : This layer is used to store data as it is received from the source of our pipeline
   - Stage : This layer is used as intermediate layer. Some of the major transmations are done to the data when it is being moved from source layer to stage layer. This layer is also useful to store data in partially denormalised form.
   - Fact : This layer will be the final layer of the data pipeline and will be used for data analysis and making business critical decisions. The data stored here is completely denormalised to the required extent of the analysis. Only minor transformations are applied on the data when it is being moved from stage layer to fact layer. But, it is important to not that, multiple tables are joined together to get this fact layer data.
