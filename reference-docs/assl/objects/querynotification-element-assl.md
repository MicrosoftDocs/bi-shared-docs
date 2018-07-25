---
title: "QueryNotification Element (ASSL) | Microsoft Docs"
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# QueryNotification Element (ASSL)

  Contains information for the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about the query to execute to determine whether a data source has been modified.  
  
## Syntax  
  
```xml  
  
<QueryNotifications>  
   <QueryNotification>  
      <Query>...</Query>  
...</QueryNotification>  
</QueryNotifications>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-n: Required element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[QueryNotifications](../collections/querynotifications-element-assl.md)|  
|Child elements|[Query](../properties/query-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.QueryNotification>.  
  
## See Also  
 [ProactiveCachingQueryBinding Data Type &#40;ASSL&#41;](data-type/proactivecachingquerybinding-data-type-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  
