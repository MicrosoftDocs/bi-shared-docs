---
title: "ProactiveCachingObjectNotificationBinding Data Type (ASSL) | Microsoft Docs"
description: Learn about the ProactiveCachingObjectNotificationBinding data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# ProactiveCachingObjectNotificationBinding Data Type (ASSL)

  Defines an abstract derived data type that represents information to the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about data source changes, either in specified tables and views or in tables and views identified through existing data bindings that require rebuilding the cache.  
  
## Syntax  
  
```xml  
  
<ProactiveCachingObjectNotificationBinding>  
   <!-- The following elements extend ProactiveCachingBinding -->  
   <NotificationTechnique>...</NotificationTechnique>  
</ProactiveCachingObjectNotificationBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[ProactiveCachingBinding](proactivecachingbinding-data-type-assl.md)|  
|Derived data types|[ProactiveCachingInheritedBinding](proactivecachinginheritedbinding-data-type-assl.md), [ProactiveCachingTablesBinding](proactivecachingtablesbinding-data-type-assl.md)|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[NotificationTechnique](../properties/notificationtechnique-element-assl.md)|  
|Derived elements|None|  
  
## Remarks  
 For more information about the **ProactiveCachingBinding** type, including a table of the inheritance hierarchy of **ProactiveCachingBinding** types, see [ProactiveCachingBinding Data Type &#40;ASSL&#41;](proactivecachingbinding-data-type-assl.md).  
  
 For more information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ProactiveCachingObjectNotificationBinding>.  
