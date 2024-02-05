---
title: "Query Processing Events Category | Microsoft Docs"
description: Learn about the event classes for the Query Processing event category.
ms.date: 07/19/2021
ms.service: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Query Processing Events Category

  The Query Processing event category has the event classes described in the following table.  
  
|**Event Class**|**Event Id**|**Description**|  
|---------------------|------------------|---------------------|  
|Query Subcube|11|Query subcube, for Usage Based Optimization.|  
|Query Subcube Verbose|12|Query subcube with detailed information. This event may have a negative impact on performance when turned on.|  
|Get Data From Aggregation|60|Answer query by getting data from aggregation. This event may have a negative impact on performance when turned on.|  
|Get Data From Cache|61|Answer query by getting data from one of the caches. This event may have a negative impact on performance when turned on.|  
|Query Cube Begin|70|Collects all Query Cube Begin events since the trace started.|  
|Query Cube End|71|Collects all Query Cube End events since the trace started.|  
|Calculate Non Empty Begin|72|Calculate non empty begin.|  
|Calculate Non Empty Current|73|Calculate non empty current.|  
|Calculate Non Empty End|74|Calculate non empty end.|  
|Serialize Results Begin|75|Serialize results begin.|  
|Serialize Results Current|76|Serialize results current.|  
|Serialize Results End|77|Serialize results end.|  
|Execute MDX Script Begin|78|Execute MDX script begin.|  
|Execute MDX Script Current|79|Execute MDX script current.|  
|Execute MDX Script End|80|Execute MDX script end.|  
|Query Dimension|81|Query dimension.|  
|VertiPaq SE Query Begin|82|Vertipaq storage engine query start time.|  
|VertiPaq SE Query End|83|Vertipaq storage engine query end time.|  
  
 For information about the columns associated with each of the Query Processing event classes, see [Query Processing Events Data Columns](query-processing-events-data-columns.md).  
