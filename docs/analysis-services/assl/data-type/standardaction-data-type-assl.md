---
title: "StandardAction Data Type (ASSL) | Microsoft Docs"
description: Learn about the StandardAction data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# StandardAction Data Type (ASSL)

  Defines a derived data type that represents any [Action](../objects/action-element-assl.md) element other than a [DrillThroughAction](drillthroughaction-data-type-assl.md) element or a [ReportAction](reportaction-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<StandardAction>  
   <!-- The following elements extend Action -->  
   <Expression>...</Expression>  
</StandardAction>  
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
|Child elements|[Expression](../properties/expression-element-assl.md)|  
|Derived elements|[Action](../objects/action-element-assl.md) ([Actions](../collections/actions-element-assl.md) collection of [Cube](../objects/cube-element-assl.md) or [Perspective](../objects/perspective-element-assl.md))|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.StandardAction>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
