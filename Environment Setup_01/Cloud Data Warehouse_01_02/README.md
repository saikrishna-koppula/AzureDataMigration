# Setting Up the Azure Cloud Database for OLAP

With our on-premise database ready, I began setting up the cloud database that will act as our OLAP source. Here’s a breakdown of each step using various Azure tools:

### Tools Used in the Project
- **Azure Data Factory** - For ETL and data ingestion.
- **Azure Synapse Analytics** - To create a SQL-like cloud environment.
- **Azure Databricks** - For data transformations and handling large datasets, using tools like PySpark.
- **Azure Data Lake Storage Gen 2** - A cost-effective cloud storage solution.
- **Azure Active Directory and Azure Key Vault** - For security, identity management, and storing sensitive credentials.

> **Note:** We’ll also use Tableau to connect to our cloud database for data visualization and analysis.

Once the pipeline is fully set up, it will allow for real-time updates—any new data in the on-premise SQL database will flow seamlessly through Azure, appearing in the Tableau dashboards.

---

## Azure Cloud Setup

### Step 1: Create the Resource Group
I started by creating a resource group named **POS_Data_ETL_Project** to organize all project resources.

### Step 2: Create Required Azure Services
Under the **POS_Data_ETL_Project** resource group, I set up the following services:
   - **Azure Databricks Service**
   - **Data Factory (V2)**
   - **Synapse Workspace**
   - **Key Vault**
   - **Data Lake Storage Account**

   ![Resource Group Image](./img/Resource%20Group%20&%20Resources.png)

### Step 3: Secure Access with Azure Key Vault
I added the SQL Server database user credentials (from our On-premises SQL Server Setup) to the **Key Vault Resource**. This setup allows our Azure services to securely access the on-premise database for data migration.

   ![Azure Key Vault Secrets Screenshot](./img/Key%20Vault%20Secrets%20SS.png)

### Step 4: Set Up Data Lake Containers
In the Data Lake storage account, I created the following containers to organize data at various stages of processing:

   - **Source:** Stores raw data as received from the pipeline’s source.
   - **Stage:** Acts as an intermediate layer. Here, significant transformations are applied, and data may be partially denormalized.
   - **Fact:** The final layer of our data pipeline, used for analysis and decision-making. Data here is fully denormalized, with only minor transformations applied as it moves from the stage layer. Multiple tables are joined to prepare this final layer.

   ![Azure Data Containers](./img/Azure%20Data%20Containers.png)

---

With these steps completed, we now have a basic version of our target database set up in Azure Cloud, ready to handle data for OLAP and integration with Tableau.