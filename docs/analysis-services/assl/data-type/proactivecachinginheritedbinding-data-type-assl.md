---
title: "ProactiveCachingInheritedBinding Data Type (ASSL) | Microsoft Docs"
description: Learn about the ProactiveCachingInheritedBinding data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# ProactiveCachingInheritedBinding Data Type (ASSL)

  Defines a derived data type that represents information to the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about data source changes in tables and views identified through existing data bindings that require rebuilding the cache.  
  
## Syntax  
  
```xml  
  
<ProactiveCachingInheritedBinding>  
   <!-- This element has no child elements that extend ProactiveCachingObjectNotificationBinding -->  
</ProactiveCachingInheritedBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[ProactiveCachingObjectNotificationBinding](proactivecachingobjectnotificationbinding-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|None|  
|Derived elements|None|  
  
## Remarks  
 For more information about the **ProactiveCachingBinding** type, including a table of the inheritance hierarchy of **ProactiveCachingBinding** types, see [ProactiveCachingBinding Data Type &#40;ASSL&#41;](proactivecachingbinding-data-type-assl.md).  
  
 For more information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ProactiveCachingInheritedBinding>.  
