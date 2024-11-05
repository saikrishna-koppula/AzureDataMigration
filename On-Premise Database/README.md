# Project Setup
## On-premises SQL Server Setup
1. Download and Install SQL Server on a system that will act as your On-Premises hardware.
2. Download SQL Server Management Studio (SSMS) and use it to host a local SQL server.
3. Create a user in the database and grant required premissions so that it can be used to log into the database when being accessed from cloud. 
4. Create the tables as per your data structure and load data into the tables.

### Loading data into the on premises SQL Server
1. 

![ER Diagram](./img/ER%20Diagram.png)


#### Features of my POS database include:
    - Uses Triggers and Stored Procedures to support one click transaction processing
    - Users are allowed to use views to look at the final data to ensure real time updates are provided to them
    - Perfoms required transformations within the transaction with the help of Triggers
    - Minimizes required human interaction with the data base for data entry