Now that your on premise database is ready, let us start creating our cloud database which will be the source for OLAP.

We are going to use the following Azure tools in building our project.

- **Azure Data Factory** - An ETL tool for data ingestion.
- **Azure Synapse Analytics** - For creating a SQL-like environment in the cloud.
- **Azure Databricks** - For data transformation and handling large datasets with tools like PySpark.
- **Azure Data Lake Storage Gen 2** - A cost-effective cloud storage solution.
- **Azure Active Directory and Azure Key Vault** - For security, identity management, and storing sensitive information.


**P.S:** We will connect Tableau (an external resource) that will connect to our database for data visualisation and analysis.

Once our pipeline is set up, it will allow for real-time updates, where new data in the on-premise SQL database will flow through the Azure system and reflect in Tableau dashboards.

## Azure Cloud Setup
1. Create a resource group for the project: **POS_Data_ETL_Project**
2. Create the following services under the resource group: Azure Databricks Service, Data Factory (V2), Synapse Workspace, Key Vault, and a Data Lake storage account. 
![Resource Group Image](./img/Resource%20Group%20&%20Resources.png)
3. Add the SQL Server database user credentials (created in the On-premises SQL Server Setup step) to Key Vault Resource. These will be used when the cloud will try to access the database for moving data.
![Azure Key Vault Secrets Screenshot](./img/Key%20Vault%20Secrets%20SS.png)
4. Navigate to data lake resource and create the following containers under Data Storage:
   - **Source :** This layer is used to store data as it is received from the source of our pipeline
   - **Stage :** This layer is used as intermediate layer. Some of the major transmations are done to the data when it is being moved from source layer to stage layer. This layer is also useful to store data in partially denormalised form.
   - **Fact :** This layer will be the final layer of the data pipeline and will be used for data analysis and making business critical decisions. The data stored here is completely denormalised to the required extent of the analysis. Only minor transformations are applied on the data when it is being moved from stage layer to fact layer. But, it is important to note that, multiple tables are joined together to get this fact layer data.
  ![Azure Data Containers](./img/Azure%20Data%20Containers.png)
 
By performing the above steps, we have set up a basic version of our target database in Azure Cloud.