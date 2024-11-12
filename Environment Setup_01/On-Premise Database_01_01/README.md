# Project Setup

## On-premises SQL Server Setup

1. I downloaded and installed SQL Server on a system that acts as my On-Premises hardware.
2. I downloaded SQL Server Management Studio (SSMS) and used it to host a local SQL server.
3. I created a user in the database and granted the required permissions so that it could be used to log into the database when accessed from the cloud.
4. I created the tables according to my data structure and loaded data into the tables.


### Loading data into the on premises SQL Server
Typically, in a real-world scenario, we would have our transactional/source database ready with data. However, for the purpose of this project we are building our own database. In a scenario where the database is already existing, you would have to understand the structure of the database and it's functionality to replicate the same or add new functionality without changing the business process in the analytical database.

For this project, I used the table structure shown below to load the data. The following ER diagram illustrates the relationships between the tables clearly.

![ER Diagram](./img/ER%20Diagram.png)

### Features of my POS database include:

- Uses Triggers and Stored Procedures to support one click transaction processing
- Users are allowed to use views to look at the final data to ensure real time updates are provided to them
- Perfoms required transformations within the transaction with the help of Triggers
- Minimizes required human interaction with the data base for data entry

P.S: I have created this database as part of my course work for **Advanced Database Management** with the help of **Dr. David Gomillion**. The database was further developed to use materialised views, views, triggers, transactions & stored procedures to act an end-to-end transaction processing system. However, we do not need it for our migration project. So let us go ahead and jump into setting up our Target Database.