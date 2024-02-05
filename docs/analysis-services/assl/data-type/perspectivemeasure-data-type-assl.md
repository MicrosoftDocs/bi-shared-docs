---
title: "PerspectiveMeasure Data Type (ASSL) | Microsoft Docs"
description: Learn about the PerspectiveMeasure data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# PerspectiveMeasure Data Type (ASSL)

  Defines a primitive data type that represents information about a measure in a [PerspectiveMeasureGroup](perspectivemeasuregroup-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<PerspectiveMeasure>  
   <MeasureID>...</MeasureID>  
   <Annotations>...</Annotations>  
</PerspectiveMeasure>  
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
|Child elements|[Annotations](../collections/annotations-element-assl.md), [MeasureID](../properties/measureid-element-assl.md)|  
|Derived elements|[Measure](../objects/measure-element-assl.md) ([Measures](../collections/measures-element-assl.md) collection of [PerspectiveMeasureGroup](perspectivemeasuregroup-data-type-assl.md))|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.PerspectiveMeasure>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
