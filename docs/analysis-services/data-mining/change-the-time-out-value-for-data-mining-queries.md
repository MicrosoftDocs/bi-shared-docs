---
title: "Change the Time-out Value for Data Mining Queries | Microsoft Docs"
description: Learn how to change the time-out value for data mining queries to prevent a prediction query from timing out.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Change the Time-out Value for Data Mining Queries
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  When you build a lift chart or execute a prediction query, sometimes it can take a long time to generate all the data required for the prediction. To prevent the query from timing out, you can change the value that controls how long the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server waits to complete a query.  
  
 The default value is 15; however, if your models are complex or the data source is large, this might not be enough. If necessary, you can increase the value significantly, to enable enough time for processing. For example, if you set **Query Timeout** to 600, the query could continue to run for up to 10 minutes.  
  
 For more information about prediction queries, see [Data Mining Query Tasks and How-tos](../../analysis-services/data-mining/data-mining-query-tasks-and-how-tos.md).  
  
### Configure the time-out value for data mining queries  
  
1.  In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], from the **Tools** menu, selection **Options**.  
  
2.  In the **Options** pane, expand **Business Intelligence Designers**.  
  
3.  Click the **Query Timeout** text box, and type a value for the number of seconds.  
  
## See Also  
 [Data Mining Query Tasks and How-tos](../../analysis-services/data-mining/data-mining-query-tasks-and-how-tos.md)   
 [Data Mining Queries](../../analysis-services/data-mining/data-mining-queries.md)  
  
  
