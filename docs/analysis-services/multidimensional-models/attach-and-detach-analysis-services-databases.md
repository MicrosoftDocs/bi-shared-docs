---
title: "Attach and Detach Analysis Services Databases | Microsoft Docs"
description: Learn to use the Attach and Detach commands to take the database offline and bring it back online with little effort.
ms.date: 05/02/2018
ms.service: azure-analysis-services
ms.custom: multidimensional-models
ms.topic: concept-article

---
# Attach and detach Analysis Services databases
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  As a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database administrator (dba), you might need to take a database offline temporarily. When you're ready, you can bring the database back online on the same server instance or on a different one. Business needs often drive these situations. For example, you might want to move the database to a different disk for better performance, gain room for database growth, or upgrade a product. For these cases and more, use the **Attach** and **Detach** commands to take the database offline and bring it back online with minimal effort.  
  
## Attach and detach commands  
 Use the **Attach** command to bring online a database that you took offline. You can attach the database to the original server instance or to another instance. When you attach a database, specify the **ReadWriteMode** setting for the database. Use the **Detach** command to take a database offline from the server.
  
## Attach and detach usage
Use the **Attach** command to bring an existing database structure online. If you attach the database in **ReadWrite** mode, you can attach it only once to a server instance. However, if you attach the database in **ReadOnly** mode, you can attach it multiple times to different server instances. You can't attach the same database more than once to the same server instance. An error occurs when you try to attach the same database more than once, even if you copy the data to separate folders.  
  
> [!IMPORTANT]  
>  If a password is required to detach the database, you must provide the same password to attach the database.  
  
Use the **Detach** command to take an existing database structure offline. When you detach a database, provide a password to protect confidential metadata.  
  
> [!IMPORTANT]  
>  To protect the content of the data files, use an access control list for the folder, subfolders, and data files.  
  
 When you detach a database, the server follows these steps.  
  
|Detaching a read/write database|Detaching a read-only database|  
|--------------------------------------|-------------------------------------|  
|1) The server issues a request for a CommitExclusive Lock on the database<br /><br /> 2) The server waits until all ongoing transactions are either committed or rolled back<br /><br /> 3) The server builds all the metadata that it must have to detach the database<br /><br /> 4) The database is marked as deleted<br /><br /> 5) The server commits the transaction|1) The database is marked as deleted<br /><br /> 2) The server commits the transaction<br /><br /> **Note:**<br /> The detaching password can't be changed for a read-only database. An error is raised if the password parameter is provided for an attached database that already contains a password.|  
  
You must execute the **Attach** and **Detach** commands as single operations. You can't combine them with other operations in the same transaction. Also, the **Attach** and **Detach** commands are atomic transactional commands. This condition means the operation either succeeds or fails. No database is left in an uncompleted state.  
  
> [!IMPORTANT]  
>  You need server or database administrator privileges to execute the **Detach** command.  
  
> [!IMPORTANT]  
>  You need server administrator privileges to execute the **Attach** command.
  
## See also
 [Move an Analysis Services Database](../../analysis-services/multidimensional-models/move-an-analysis-services-database.md)   
 [Database ReadWriteModes](../../analysis-services/multidimensional-models/database-readwritemodes.md)   
 [Switch an Analysis Services database between ReadOnly and ReadWrite modes](../../analysis-services/multidimensional-models/switch-an-analysis-services-database-between-readonly-and-readwrite-modes.md)   
 [Detach Element](../xmla/xml-elements-commands/detach-element.md)   
 [Attach Element](../xmla/xml-elements-commands/attach-element.md)  
  
