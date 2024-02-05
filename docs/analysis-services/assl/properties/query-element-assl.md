---
title: "Query Element (ASSL) | Microsoft Docs"
description: Learn about the Query property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# Query Element (ASSL)

  Contains the text of the query to execute for the notification.  
  
## Syntax  
  
```xml  
  
<QueryNotification>  
   <Query>...</Query>  
</QueryNotification>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[QueryNotification](../objects/querynotification-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **Query** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.QueryNotification>.  
  
## See Also  
 [ProactiveCachingQueryBinding Data Type &#40;ASSL&#41;](../data-type/proactivecachingquerybinding-data-type-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
