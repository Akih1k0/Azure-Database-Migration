# Azure Database Migration

## Overview
This project involves architecting and implementing a cloud-based database system on Microsoft Azure, demonstrating proficiency in cloud engineering. The process includes establishing a production environment database, migration to Azure SQL Database, and addressing key considerations such as data backup and restoration.

The project will also involve the simulation of disaster recovery scenarios, with a focus on mitigating potential data loss. Exploring geo-replication and failover configuration will be essential for ensuring continuous data availability under challenging conditions.

To bolster security measures, Microsoft Entra ID integration will be employed to define access roles, providing an additional layer of control and protection. This approach reflects a commitment to implementing robust, secure, and resilient solutions within the Azure environment.

## Milestone 1 & 2: Setup
### Virtual Machine Setup
**Azure VM Successfully Provisioned:**
- Azure VM Name: azure-database-migration
- VM Size: Standard B2ms (2 vcpus, 8 GiB memory)
- Operating System: Windows (Windows 11 Pro)

**Remote Desktop Connection Established:**
- RDP connection was used to connect to the Virtual Machine through microsoft remote desktop.

### SQL Server Installation
- SQL Server and SQL Server Management Studio (SSMS) installed on the Azure VM.

### Production Database Creation
- AdventureWorks backup file downloaded and copied to `C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\Backup\AdventureWorks2022.bak`
- AdventureWorks database successfully restored on the Azure VM.

## Task Accomplishments
- Task 1: VM provisioned successfully.
- Task 2: Remote desktop connection established.
- Task 3: SQL Server and SSMS installed on the VM.
- Task 4: AdventureWorks database restored.

## Insights and Learnings
- The virtual machine setup and SQL Server installation were smooth.
- Challenges faced during database restoration were minimal, and the process was successful.
- Adding the backup file to the backup folder in the vm allowed for the restoration to run smoothly.

## Next Steps
- ### Milestone 3: Migrate to Azure SQL Database:
    - Task 1: Setup Azure SQL Database.
    - Task 2: Prepare for Migration.
    - Task 3: Connect to Azure SQL Database.
    - Task 4: Schema Migration.
    - Task 5: Data Migration.
    - Task 6: Validate Migration Success.