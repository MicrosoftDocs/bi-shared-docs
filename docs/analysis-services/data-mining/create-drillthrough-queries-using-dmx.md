---
title: "Create Drillthrough Queries using DMX | Microsoft Docs"
description: Learn how to create drillthrough queries DMS to retrieve case data and structure data in SQL Server Management Studio.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: how-to

---
# Create drillthrough queries by using DMX
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  For all models that support drillthrough, you can retrieve case data and structure data by creating a DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or any other client that supports DMX.  
  
> [!IMPORTANT]  
>  To view the data, you must enable drillthrough and have the necessary permissions.  
  
## Specifying drillthrough options  
 The general syntax for retrieving model cases and structure cases is as follows:  
  
```  
SELECT <model column list>, StructureColumn('<structure column name>') FROM <modelname>.CASES  
```  
  
 For more information about using DMX queries to return case data, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) and [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).  
  
## Examples  
 The following DMX query returns the case data for a specific product series from a time series model. The query also returns the column **Amount**, which wasn't used in the model but is available in the mining structure.  
  
```  
SELECT [DateSeries], [Model Region], Quantity, StructureColumn('Amount') AS [M200 Pacific Amount]  
FROM Forecasting.CASES  
WHERE [Model Region] = 'M200 Pacific'  
```  
  
 In this example, the query uses an alias to rename the structure column. If you don't assign an alias to the structure column, the column is returned with the name 'Expression'. This name is the default for all unnamed columns.  
  
## See also  
 [Drillthrough Queries &#40;Data Mining&#41;](../../analysis-services/data-mining/drillthrough-queries-data-mining.md)   
 [Drillthrough on Mining Structures](../../analysis-services/data-mining/drillthrough-on-mining-structures.md)  
  
  
