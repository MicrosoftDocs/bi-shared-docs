---
title: "Compatibility level for tabular models in Analysis Services | Microsoft Docs"
ms.date: 03/23/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Compatibility level for tabular models

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

  The *compatibility level* refers to release-specific behaviors in the Analysis Services engine. For example, DirectQuery and tabular object metadata have different implementations depending on the compatibility level. In-general, you should choose the latest compatibility level supported by your servers.

  **The latest supported compatibility level is 1500** 
  
Major features in the 1500 compatibility level include:

*  [Calculation groups](calculation-groups.md)
*  [Many-to-many relationships](../what-s-new-in-sql-server-analysis-services.md#many-to-many-relationships-in-tabular-models)
*  Supported in [Power BI Premium](https://docs.microsoft.com/power-bi/service-premium-connect-tools)
  
## Supported compatibility levels by version
  
| Compatibility level | Server version |
| ------------------- | -------------- |
|1500|Power BI Premium, Azure Analysis Services, SQL Server 2019 | 
|1400|Azure Analysis Services, SQL Server 2019, SQL Server 2017 |  
|1200|Azure Analysis Services, SQL Server 2019, SQL Server 2017, SQL Server 2016| 
|1103|SQL Server 2017*, SQL Server 2016, SQL Server 2014, SQL Server 2012 SP1|  
|1100|SQL Server 2017*, SQL Server 2016, SQL Server 2014, SQL Server 2012 SP1, SQL Server 2012| 

\* 1100 and 1103 compatibility levels are deprecated in SQL Server 2017.
  
## Set compatibility level 

 When creating a new tabular model project in Visual Studio, you can specify the compatibility level on the **Tabular model designer** dialog. 
  
 ![ssas_tabularproject_compat1200](../../analysis-services/tabular-models/media/ssas-tabularproject-compat1200.png)  
  
 If you select the **Do not show this message again** option, all subsequent projects will use the compatibility level you specified as the default. You can change the default compatibility level in SSDT in **Tools** > **Options**.  
  
 To upgrade a tabular model project in SSDT, set  the **Compatibility Level** property in the model **Properties** window. Keep in-mind, upgrading the compatibility level is irreversible.
  
## Check compatibility level for a tabular database in SSMS 

 In SSMS, right-click the database name > **Properties** > **Compatibility Level**.  
  
## Check supported compatibility level for a server in SSMS

 In SSMS, right-click the server name>  **Properties** > **Supported Compatibility Level**.  

 This property specifies the highest compatibility level of a database that will run on the server. The supported compatibility level is read-only cannot be changed.
 
> [!NOTE]  
>  In SSMS, when connected to a SQL Server Analysis Services server, Azure Analysis Services server, or Power BI Premium workspace, the Supported Compatibility Level property will show 1200. This is a known issue and will be resolved in an upcoming SSMS update. When resolved, this property will show the highest supported compatibility level. 
  
## See also  
 [Compatibility Level of a multidimensional database](../../analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services.md)   
 [Create a new tabular model project](../../analysis-services/tabular-models/create-a-new-tabular-model-project-analysis-services.md)  
  
  
