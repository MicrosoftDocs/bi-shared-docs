---
title: "DrillThroughAction Data Type (ASSL) | Microsoft Docs"
description: Learn about the DrillThroughAction data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# DrillThroughAction Data Type (ASSL)

  Defines a derived data type that represents a drillthrough action.  
  
## Syntax  
  
```xml  
  
<DrillThroughAction>  
   <!-- The following elements extend Action -->  
   <Default>...</Default>  
   <Columns>...</Columns>  
</DrillThroughAction>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Action](action-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Columns](../collections/columns-element-assl.md), [Default](../properties/default-element-assl.md)|  
|Derived elements|[Action](../objects/action-element-assl.md) ([Actions](../collections/actions-element-assl.md), collection of [Cube](../objects/cube-element-assl.md), or [Perspective](../objects/perspective-element-assl.md))|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DrillThroughAction>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
