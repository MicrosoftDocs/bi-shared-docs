---
title: "Tools for Analysis Services | Microsoft Docs"
ms.date: 10/23/2019
ms.prod: sql
ms.technology: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
---
# Tools for Analysis Services

[!INCLUDE[ssas-appliesto-sqlas-aas](../includes/ssas-appliesto-sqlas-aas.md)]

  Find the tools and applications you'll need for building Analysis Services models and managing deployed databases.  

## Create and deploy models  

Tabular and multidimensional model projects are created by using project templates in Visual Studio with Analysis Services projects extensions (VSIX). Project templates provide model designers and wizards for creating the data model objects that comprise an Analysis Services solution. Analysis Services projects extensions are supported on all Visual Studio 2017 and later editions, including the free Community edition. 

[Download Visual Studio 2019](https://visualstudio.microsoft.com/downloads/)

[Download Analysis Services projects extension](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects)

SQL Server Data Tools (SSDT) has been an integral part of creating Analysis Services solutions since SQL 2005. With the introduction of project extensions in Visual Studio, SSDT has been phased out in favor of Visual Studio with Analysis Services projects. Much of the Analysis Services documentation here refers to SSDT, and images often show SSDT windows and dialogs. While Visual Studio 2017 and later with Analysis Services extensions are installed differently and offer even more functionality, the user interface in Visual Studio is much the same as SSDT. Documentation will be updated with new naming and images over time.

## Administer servers and databases  

### Azure portal

The [Azure portal](https://portal.azure.com/) is the primary tool for creating and managing Azure Analysis Services resources. To learn more about the portal and other tools used with Azure Analysis Services, see [Azure Analysis Services tools](/azure/analysis-services/analysis-services-overview#use-the-tools-you-already-know).

### SQL Server Management Studio

 SQL Server Management Studio (SSMS) is the primary administration tool for Azure Analysis Services and SQL Server Analysis Services servers and deployed model databases. SSMS is a free web download updated monthly. 
  
**[Download SQL Server Management Studio](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)** 
  
#### SQL Server Profiler 

 [SQL Server Profiler](/sql/tools/sql-server-profiler/sql-server-profiler), installed with SSMS, is a graphical user interface to SQL Trace for monitoring a server instance. You can capture and save data about each event to a file or table to analyze later. 

#### XEvents
  
 SSMS includes extended events (xEvents), providing a lightweight alternative to SQL Server Profiler traces used for monitoring activity and diagnosing problems on Analysis Services servers. See [Monitor Analysis Services with SQL Server Extended Events](../analysis-services/instances/monitor-analysis-services-with-sql-server-extended-events.md) to learn more.  
  
### PowerShell

 PowerShell commands are used to perform many database administrative tasks in both Azure Analysis Services and SQL Server Analysis Services. To learn more, see [PowerShell reference](../analysis-services/powershell/analysis-services-powershell-reference.md).

 Azure Analysis Services has its own set of PowerShell commands for managing Azure resources. To learn more, see [Manage Azure Analysis Services with PowerShell](/azure/analysis-services/analysis-services-powershell).


## See also

 [Azure Analysis Services documentation](/azure/analysis-services/)   
 [Azure Analysis Services REST API](/rest/api/analysisservices/)   
 [Analysis Services scripting and API references](/bi-reference/)   


