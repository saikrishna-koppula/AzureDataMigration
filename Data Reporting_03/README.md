## Connecting Tableau to Azure Synapse SQL Database

After completing the data loading process, I connected Tableau to our Azure Synapse SQL Database to perform the final analysis. Here’s a breakdown of the steps I followed:

### Step 1: Open Tableau and Start the Connection
I opened Tableau on my system and clicked on **More** under the "Connect to a Server" section to view all available data source options.

![Tableau source options](./img/Tableau%20Source%20Options.png)

### Step 2: Select Azure Synapse Analytics
From the list, I selected **Azure Synapse Analytics**. Tableau informed me of the necessary drivers needed for the connection, which appeared in a prompt like this:

![Tableau Driver Requirement](./img/Tableau%20Driver%20Requirement.png)

### Step 3: Check Driver Installation
After I installed the required drivers, I was able to proceed to the connection setup screen without any additional installation steps. The screen looked like this:

![Tableau Source Connection](./img/Tableau%20Source%20Connection.png)

### Step 4: Authenticate and Secure the Connection
I chose my preferred authentication method for secure access, entered my credentials, and successfully connected to the database.

### Step 5: Ready for Analysis
With the connection established, I am now ready to start analyzing the data in Tableau.

### Additional Information
For more details on this process, refer to [Tableau’s official documentation](https://help.tableau.com/current/pro/desktop/en-us/examples_azure_sql_dw.htm) for connecting to Azure Synapse Analytics.

### Dashboard:

Here’s a snapshot of the Tableau dashboard I built after successfully connecting to our Azure Synapse SQL Database. This dashboard provides key insights based on our data, highlighting trends and metrics that support our analysis goals.

![Tableau Dashboard](./img/Dashboard%201.png)

*P.S.: Please note that the data is not from the real world, and the charts might be representing some assumptions.*