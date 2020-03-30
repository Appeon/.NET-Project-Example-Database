# <b>Sample Database Readme</b>

This repository provides the example database backup files necessary for setting up the database to work with the [SnapObjects-Example](https://github.com/Appeon/SnapObjects-Example), and [.NET-DataStore-Example](https://github.com/Appeon/.NET-DataStore-Example). 

The origin of all the database backup files is [AdventureWorks2012](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks2012) from Microsoft. Because AdventureWorks2012 is only for SQL Server, we have ported it to Oracle, SQL Anywhere or PostgreSQL and created the database backup files for these databases as well, so you can run the examples with either SQL Server, Oracle, SQL Anywhere or PostgreSQL.

### Supported database versions 

- AdventureWorks_for_sqlserver: SQL server 2012 or later
- AdventureWorks_for_oracle: Oracle 12c or later
- AdventureWorks_for_sqlanywhere: SQL Anywhere 17.0.9.4803 or later
- AdventureWorks_for_postgresql: PostgreSQL 10 or later

### Steps to restore AdventureWorks_for_SQL Server

1. Open SQL Server Management Studio and connect to the target SQL Server instance.
2. Right-click on the Databases node, and select Restore Database.
3. On the General page, use the Source section to specify the source and location of the backup database (AdventureWorks_for_sqlserver.bak) to restore.  
4. In the Destination section, the Database box is automatically populated with the name of the database to be restored. To change the name of the database, enter the new name in the Database box, for example, AdventureWorks.
5. Click **OK**. This will initiate the database restore. After it completes, you will have the AdventureWorks database installed on your SQL Server instance.

### Steps to restore AdventureWorks_for_oracle

1. Create an AdventureWorks database instance on the Oracle database server; 

2. Copy the AdventureWorks_for_oracle.DMP file to the dpdump folder of the AdventureWorks database instance;

3. Execute the following command line to restore the database (the username/password in the command line shall be replaced with the actual database username/password):

   ```
   impdp username/password@AdventureWorks schemas=HumanResources,Person,Production,Purchasing,Sales dumpfile=AdventureWorks_for_oracle.DMP
   ```

   Note: It is possible that some data in the Description column of the PRODUCTION.PRODUCTDESCRIPTION table cannot be successfully imported during the Restore process. This issue can be ignored because it won't affect the database access.

### Steps to restore AdventureWorks_for_sqlanywhere

1. Find the dbsrv17.exe file in the Bin64 folder of the SQL Anywhere 17 installation directory;
2. Run dbsrv17.exe and load AdventureWorks_for_sqlanywhere.db.

### Steps to restore AdventureWorks_for_PostgreSQL

1. Start pgAdmin;
2. Create a new database AdventureWorks within the server you are using; 
3. Right click the database and choose Restore; 
4. Use the Browser button to select the database backup file AdventureWorks_for_postgresql.bak;
5. Select Restore to start restoring the database.

