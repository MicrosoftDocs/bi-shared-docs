---
title: "ProactiveCachingBinding Data Type (ASSL) | Microsoft Docs"
description: Learn about the ProactiveCachingBinding data type element in the Analysis Services Scripting Language (ASSL) schema.
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
# ProactiveCachingBinding Data Type (ASSL)

  Defines an abstract derived data type that represents information to the [ProactiveCaching](../objects/proactivecaching-element-assl.md) element about data source changes that require rebuilding the cache, or about the status of the rebuilding process.  
  
## Syntax  
  
```xml  
  
<ProactiveCachingBinding>  
   <!-- ProactiveCachingBinding is an abstract base class with no child elements -->  
</ProactiveCachingBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Binding](binding-data-type-assl.md)|  
|Derived data types|[ProactiveCachingIncrementalProcessingBinding](proactivecachingincrementalprocessingbinding-data-type-assl.md), [ProactiveCachingObjectNotificationBinding](proactivecachingobjectnotificationbinding-data-type-assl.md), [ProactiveCachingQueryBinding](proactivecachingquerybinding-data-type-assl.md)|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|None|  
|Derived elements|None|  
  
## Remarks  
 For more information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ProactiveCachingBinding>.  
  
## Inheritance Hierarchy of ProactiveCachingBinding Types  
 The following hierarchy shows the inheritance of **ProactiveCachingBinding** types.  
  
 [Binding](binding-data-type-assl.md) element  
  
 **ProactiveCachingBinding** element  
  
 [ProactiveCachingObjectNotificationBinding](proactivecachingobjectnotificationbinding-data-type-assl.md) element  
  
 [ProactiveCachingInheritedBinding](proactivecachinginheritedbinding-data-type-assl.md) element  
  
 [ProactiveCachingTablesBinding](proactivecachingtablesbinding-data-type-assl.md) element  
  
 [ProactiveCachingQueryBinding](proactivecachingquerybinding-data-type-assl.md) element  
  
 [ProactiveCachingIncrementalProcessingBinding](proactivecachingincrementalprocessingbinding-data-type-assl.md) element  

  
  
