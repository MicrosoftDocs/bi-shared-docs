---
title: "TableNotification Element (ASSL) | Microsoft Docs"
description: Learn about the TableNotification object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# TableNotification Element (ASSL)

  Contains information for the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about a table or view in a data source that has been modified.  
  
## Syntax  
  
```xml  
  
<TableNotifications>  
   <TableNotification>  
      <DbTableName>...</DbTableName>  
      <DbSchemaName>...</DbSchemaName>  
...</TableNotification>  
</TableNotifications>  
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
|Parent elements|[TableNotifications](../collections/tablenotifications-element-assl.md)|  
|Child elements|[DbSchemaName](../properties/dbschemaname-element-assl.md), [DbTableName](../properties/dbtablename-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.TableNotification>.  
  
## See Also  
 [ProactiveCachingTablesBinding Data Type &#40;ASSL&#41;](../data-type/proactivecachingtablesbinding-data-type-assl.md)   
 [ProactiveCachingObjectNotificationBinding Data Type &#40;ASSL&#41;](../data-type/proactivecachingobjectnotificationbinding-data-type-assl.md)   
 [ProactiveCachingBinding Data Type &#40;ASSL&#41;](../data-type/proactivecachingbinding-data-type-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  
