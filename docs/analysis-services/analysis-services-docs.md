---
title: "Analysis Services documentation overview| Microsoft Docs"
ms.date: 03/12/2020
ms.prod: sql
ms.technology: analysis-services
ms.topic: overview
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Understanding Analysis Services documentation

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

If you're using Azure Analysis Services, SQL Server Analysis Services, or Power BI Premium datasets, reading this article will help you find the documentation you're looking for.

## One engine - three platforms

Analysis Services exists on three different platforms, in **Azure Analysis Services**, on-premises with **SQL Server**, and under the hood, Analysis Services powers **Power BI Premium** workspaces and datasets. From a documentation perspective, this presents a unique challenge where some documentation applies to only one platform, like Azure Analysis Services, or applies to all platforms. For example, how you provision an Analysis Services resource in Azure is quite different from how you create a server instance in SQL Server Analysis Services. On the other hand, how you use Visual Studio to create a tabular model project and deploy it is much the same, regardless of platform. Or, how SQL Server Profiler is used to capture data about process events in the Analysis Services engine.

All Analysis Services documentation, regardless of platform, exists in [Microsoft Docs](https://docs.microsoft.com/) (docs.microsoft.com). To reduce redundancy, where possible, articles that apply to more than one platform are included here in the core Analysis Services documentation.

### Azure Analysis Services

If you're using Azure Analysis Services, it's best to start with [Azure Analysis Services documentation](https://docs.microsoft.com/azure/analysis-services/). This is where you can learn about Analysis Services' specific implementation in Azure. For example, using the Azure portal to create an Analysis Services server resource in your Azure subscription, configure a firewall, or configure scale-out to create a *query pool* where queries are distributed among *query replicas*.

### Power BI Premium

If you are using Power BI Premium, it's best to start with the [Power BI Premium documentation]

### SQL Server Analysis Services

If you are using SQL Server 2016 or later Analysis Services for on-premises tabular or multidimensional model solutions, you're already where you need to be. The Table of Contents (ToC) to the left includes all of the documentation for SQL Server Analysis Services. Use the version selector above the ToC to see only those articles that apply the version you are using.

Looking for SQL Server 2014 Analysis Services documentation? - SQL Server 2014 Analysis Services documentation is kept separate from later version documentation. This is due to changing documentation models used on docs.microsoft.com compared to MSDN, where SQL Server 2014 and earlier Books Online documentation was originally published. Go to [SQL Server 2014 Analysis Services documentation](https://docs.microsoft.com/sql/analysis-services/analysis-services?view=sql-server-2014). Need to go back even further? See [SQL Server previous versions documentation](https://docs.microsoft.com/previous-versions/sql/).


## Contribute

Analysis Services documentation, like this article, are open-source. The Analysis Services team does its best to create articles that help you throughout all phases of your Analysis Services solution.

To learn more about how you can contribute, see the [Docs contributor guide](https://docs.microsoft.com/contribute/).


## See also

[What is Analysis Services?](analysis-services-overview.md)