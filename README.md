# Azure Database Migration
This project involves architecting and implementing a cloud-based database system on Microsoft Azure, demonstrating proficiency in cloud engineering. The process includes establishing a production environment database, migration to Azure SQL Database, and addressing key considerations such as data backup and restoration.

## Milestone 1 & 2: Setup
**Azure VM Successfully Provisioned:**
- Azure VM Name: azure-database-migration
- VM Size: Standard B2ms (2 vcpus, 8 GiB memory)
- Operating System: Windows (Windows 11 Pro)

**Remote Desktop Connection Established:**
- RDP connection was used to connect to the Virtual Machine through microsoft remote desktop.

**Production Database Creation:**
- AdventureWorks backup file downloaded and copied to `C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\Backup\AdventureWorks2022.bak`
- AdventureWorks database successfully restored on the Azure VM.

## Milestone 3: Migration
**Migration to SQL Database:**
- Once a connection to the local database was established a connection to the Azure SQL database was made allowing for the use of schema compare to allow for seemless migration.
- Through the use of queries the migrated data was compared to the local database to ensure that all data was transfered successfully.

**Data Comparison**

Local:
![local data](images/local_Q1.png)
Migrated:
![Migrated data](images/migrated_Q1.png)


## Milestone 4: Backup
**Backup data:**
- A backup file of the AdventureWorks database was stored on the local machine and a blob on Microsoft Azure, allowing for further security to the data being recoverable. 
- A weekly backup maintainance plan was created in microsoft SSMS. This was first tested in the Development Environment and then replicated to the live environment.
- Using these techniques creates a safeguard from data loss and corruption. The main risks prevented are accidental deletion or alterations to data that could cause corruption and errors.

## Milestone 5: Disaster Recovery
By mimicking data loss a disaster recovery situation can be simulated to ensure the backup and restoration is applied. By using SQL queries the data was deleted and corrupted.

```sql
-- Intentinal Deletion
DELETE TOP (100)
FROM HumanResources.EmployeePayHistory;

-- Data Corruption
UPDATE TOP (100) HumanResources.EmployeePayHistory
SET Rate = NULL;
```
This query deletes the first 100 rows and then sets the rate to Null. This was the disaster situation and to recover the data that was deleted and altered the SQL database was recovered to the backup point from 1 hour ago. The data was the checked:

![recovered data](images\employee_pay_table_recovered.png)

## Insights and Learnings
- The virtual machine setup and SQL Server installation were smooth.
- Challenges faced during database restoration were minimal, and the process was successful.
- Adding the backup file to the backup folder in the vm allowed for the restoration to run smoothly.
- Automated backups will also backup corrupted data if the data is not recovered.
- Development environments are good test areas.