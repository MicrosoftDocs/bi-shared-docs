---
title: "PerspectiveDimension Data Type (ASSL) | Microsoft Docs"
description: Learn about the PerspectiveDimension data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# PerspectiveDimension Data Type (ASSL)

  Defines a primitive data type that represents information about a dimension in a perspective.  
  
## Syntax  
  
```xml  
  
<PerspectiveDimension>  
   <CubeDimensionID>...</CubeDimensionID>  
   <Attributes>...</Attributes>  
   <Hierarchies>...</Hierarchies>  
      <Annotations>...</Annotations>  
</PerspectiveDimension>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Annotations](../collections/annotations-element-assl.md), [Attributes](../collections/attributes-element-assl.md), [CubeDimensionID](../properties/cubedimensionid-element-assl.md), [Hierarchies](../collections/hierarchies-element-assl.md)|  
|Derived elements|[Dimension](../objects/dimension-element-assl.md) ([Dimensions](../collections/dimensions-element-assl.md) collection of [Perspective](../objects/perspective-element-assl.md))|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.PerspectiveDimension>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
