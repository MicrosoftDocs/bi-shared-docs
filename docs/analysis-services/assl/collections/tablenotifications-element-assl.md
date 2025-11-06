---
title: "TableNotifications Element (ASSL) | Microsoft Docs"
description: Learn about the TableNotifications collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# TableNotifications Element (ASSL)

  Contains the collection of [TableNotification](../objects/tablenotification-element-assl.md) elements that provide information for the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about tables or views in a data source that have been modified.  
  
## Syntax  
  
```xml  
  
<ProactiveCachingTablesBinding>  
   <TableNotifications>  
      <TableNotification>...</TableNotification>  
...</TableNotifications>  
</ProactiveCachingTablesBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[ProactiveCachingTablesBinding](../data-type/proactivecachingtablesbinding-data-type-assl.md)|  
|Child elements|[TableNotification](../objects/tablenotification-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.TableNotificationCollection>.  
