---
title: "Tools and applications used in Analysis Services | Microsoft Docs"
ms.date: 10/22/2019
ms.prod: sql
ms.technology: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
---
# Tools and applications used in Analysis Services

[!INCLUDE[ssas-appliesto-sqlas-aas](../includes/ssas-appliesto-sqlas-aas.md)]

  Find the tools and applications you'll need for building Analysis Services models and managing deployed databases.  

## Analysis Services model designers  

Tabular and multidimensional model projects are created by using project templates in SQL Server Data Tools (SSDT), a Visual Studio shell, or Visual Studio 2019 and later with Analysis Services projects extensions (VSIX). Project templates provide model designers and wizards for creating the data model objects that comprise an Analysis Services solution. 

**SQL Server Data Tools (SSDT)** - Beginning in early 2019, SSDT is no longer updated. Tabular model projects at the 1500 and higher compatibility levels are not supported. Analysis Services project functionality has been moved to Analysis Services projects extensions in Visual Studio. It's recommended you use Visual Studio 2017 or later with Analysis Services projects extensions.

**Visual Studio with Analysis Services projects** - Analysis Services projects extensions are supported on all Visual Studio 2017 and later editions, including the free Community edition. Visual Studio with project extensions offer many advantages over earlier installations of SSDT. 

[Download Visual Studio 2019](https://visualstudio.microsoft.com/downloads/)

[Download Analysis Services projects extension](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects)

The names SQL Server Data Tools and SSDT have been synonymous with creating Analysis Services solutions since SQL 2005. Much of the Analysis Services documentation here refers to SSDT, and images often show SSDT windows and dialogs. While Visual Studio 2017 and later with Analysis Services extensions are installed differently and offer even more functionality, the user interface in Visual Studio is much the same as SSDT. Documentation will be updated with new naming and images over time.

## Administrative tools  
  
 SQL Server Management Studio (SSMS) is the primary administration tool for all SQL Server features, including Analysis Services. SSMS is a free web download updated monthly. 
  
**[Download SQL Server Management Studio](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)** 
  
 SSMS includes extended events (xEvents), providing a lightweight alternative to SQL Server Profiler traces used for monitoring activity and diagnosing problems on SQL Server 2016 and Azure Analysis Services servers. See [Monitor Analysis Services with SQL Server Extended Events](../analysis-services/instances/monitor-analysis-services-with-sql-server-extended-events.md) to learn more.  
  
### SQL Server Profiler 

 Although it's officially deprecated in favor of xEvents, SQL Server Profiler provides a familiar approach for monitoring connections, MDX query execution, and other server operations. SQL Server Profiler is installed by default. You can find it with SQL Server applications on Apps in Windows.  
  
### PowerShell

 You can use PowerShell commands to perform many administrative tasks. See [PowerShell reference](../analysis-services/powershell/analysis-services-powershell-reference.md) for more information.
 
  
