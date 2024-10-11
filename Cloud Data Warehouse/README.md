
Now that your on premise database is ready, let us start creating our cloud database which will be the source for OLAP.

## Azure Cloud Setup
1. Create a resource group for the project: rg-db-migration-project
2. Create the following services under the resource group: Azure Databricks Service, Data Factory (V2), Synapse Workspace, Key Vault, and a Data Lake storage account. <Image>
3. Add the SQL Server database user credentials (created in the On-premises SQL Server Setup step) to Key Vault.
4. Navigate to data lake resource and create the following containers under Data Storage:
   - **Source :** This layer is used to store data as it is received from the source of our pipeline
   - **Stage :** This layer is used as intermediate layer. Some of the major transmations are done to the data when it is being moved from source layer to stage layer. This layer is also useful to store data in partially denormalised form.
   - **Fact :** This layer will be the final layer of the data pipeline and will be used for data analysis and making business critical decisions. The data stored here is completely denormalised to the required extent of the analysis. Only minor transformations are applied on the data when it is being moved from stage layer to fact layer. But, it is important to not that, multiple tables are joined together to get this fact layer data.
