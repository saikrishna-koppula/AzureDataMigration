### Data Loading

I will use Azure Synapse Analytics for loading the data from data lake to a Synapse SQL database. Synapse Analytics has a built-in connection to the Azure Data Lake, allowing direct querying of data. There are 2 types of SQL databases in Synapse: Serverless SQL Database and Dedicated SQL Database. We are going to use Serverless SQL Database.

I created a Synapse Analytics workspace. Once the workspace is created, I can then write a statement in SQL to use the file from the container in ADF and load data into a Table/View. Before writing the SQL statement, I cerated a serverless DB **Fact_POS**. Then I have written a SQL statemetn that creates a view for one table. NOw I have to do the same for all tables. I automated this process by creating a stored procedure that takes a parameter (View Name) and creates a base view for all the tables. Below are some screenshots.

![Views Stored Procedure Screenshot](./img/Views%20Stored%20Procedure.png)

This stored procedure creates a view for each table present inside the factlayer. It is important to note that we don't need this step in our pipeline rather we need to run this procedure onky once as we need to create the views only once. However, if any changes are made tables structures on any tables, then we need to manually run this procedure once again. Below is a screenshot of views created after the procedure is run.

![Views Created Screenshot](./img/Views%20Created%20Screenshot.png)