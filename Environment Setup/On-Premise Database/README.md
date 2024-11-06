# Project Setup

## On-premises SQL Server Setup

1. Download and Install SQL Server on a system that will act as your On-Premises hardware.
2. Download SQL Server Management Studio (SSMS) and use it to host a local SQL server.
3. Create a user in the database and grant required premissions so that it can be used to log into the database when being accessed from cloud.
4. Create the tables as per your data structure and load data into the tables.

### Loading data into the on premises SQL Server

Typically, in a real-world scenario, we would have our transactional/source database ready with data. However, for the purpose of this project we are building our own database. In a scneario where the database is already existing, you would have to understand teh structre of the database and it's functionlaity to replicate the same or add new functionality without changing the business process in the analytical database.

I have used the below table structure to load my data. The following ER diagram demonstrates a clear relation between each table.

![ER Diagram](./img/ER%20Diagram.png)

### Features of my POS database include:

- Uses Triggers and Stored Procedures to support one click transaction processing
- Users are allowed to use views to look at the final data to ensure real time updates are provided to them
- Perfoms required transformations within the transaction with the help of Triggers
- Minimizes required human interaction with the data base for data entry

P.S: I have created this database as part of my course work for **Advanced Database Management** with the help of **Dr. David Gomillion**. The database was further developed to use materialised views, views, triggers, transactions & stored procedures to act an end-to-end transaction processing system. However, we do not need it for our migration project. So let us go ahead and jump into setting up our Target Database.