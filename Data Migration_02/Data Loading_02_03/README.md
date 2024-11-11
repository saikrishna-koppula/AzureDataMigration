# Data Loading with Azure Synapse Analytics

In this stage, I used **Azure Synapse Analytics** to load the data from **Azure Data Lake** into a **Synapse SQL database**. Synapse Analytics provides a built-in connection to Azure Data Lake, enabling direct querying of data. There are two types of SQL databases available in Synapse: **Serverless SQL Database** and **Dedicated SQL Database**. For this project, I used the **Serverless SQL Database**.

---

## Creating the Synapse Analytics Workspace

1. I created a Synapse Analytics workspace.
   
2. After creating the workspace, I wrote a SQL statement to load data directly from the data lake container into a **Table/View** within the Synapse workspace.
   
3. To organize the data, I created a **serverless database** named **Fact_POS**.

---

## Automating View Creation with a Stored Procedure

Initially, I wrote a SQL statement to create a view for a single table. To automate the process for all tables, I created a **stored procedure** that takes a parameter (the **View Name**) and generates a base view for each table in the **factlayer** container.

Below is a screenshot of the stored procedure:

![Views Stored Procedure Screenshot](./img/Views%20Stored%20Procedure.png)

- This stored procedure generates a view for every table present in the `factlayer`.
- Importantly, this procedure only needs to be executed **once** to create the views. However, if there are any structural changes to the tables, this procedure will need to be manually re-run to update the views accordingly.

After running the procedure, the views were created successfully. Below is a screenshot showing the views created:

![Views Created Screenshot](./img/Views%20Created%20Screenshot.png)
