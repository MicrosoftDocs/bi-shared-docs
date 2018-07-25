---
title: "TableNotifications Element (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# TableNotifications Element (ASSL)

  Contains the collection of [TableNotification](objects/tablenotification-element-assl.md) elements that provide information for the [ProactiveCaching](objects/proactivecaching-element-assl.md) element about tables or views in a data source that have been modified.  
  
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
|Parent elements|[ProactiveCachingTablesBinding](data-type/proactivecachingtablesbinding-data-type-assl.md)|  
|Child elements|[TableNotification](objects/tablenotification-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.TableNotificationCollection>.  
