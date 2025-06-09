---
title: "Verify SQL Server Analysis Services cumulative update build version | Microsoft Docs"
description: Learn how to verify the the SQL Server Analysis Services cumulative update build package version number.
ms.date: 01/05/2021
ms.service: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2016"
---

# Verify Analysis Services cumulative update build version

[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]

Beginning with SQL Server 2017, the Analysis Services build version number and SQL Server Database Engine build version number do not match. While both Analysis Services and the Database Engine use the same installer, the build systems each use are separate.

 In some cases, it may be necessary to verify if a Cumulative Update (CU) build package has been applied and Analysis Services components have been updated. You can verify by comparing the build version numbers of Analysis Services component files installed on your computer with the  build version numbers for a particular CU.

## Verify component file version

To verify component file version, 

1. Go to [SQL Server 2017 build versions](/troubleshoot/sql/releases/sqlserver-2017/build-versions). 
2. In **SQL Server 2017 cumulative update (CU) builds**, click the **Knowledge Base Number** for the build you want to verify.
3. In the **Cumulative Update (#) for SQL Server 2017** article, in the **Cumulative Update package information** section, expand **Cumulative update package file information**.
4. In the **SQL Server 2017 Analysis Services** table, check the File version for the **msmdsrv.exe** component file. If the CU has been applied, the file version number should match the msmdsrv.exe file installed on your computer.

## See also  

[Install SQL Server Servicing Updates](/sql/database-engine/install-windows/install-sql-server-servicing-updates)  

[Update Center for Microsoft SQL Server](/sql/database-engine/install-windows/latest-updates-for-microsoft-sql-server)
  
