---
title: "MeasureBinding Data Type (ASSL) | Microsoft Docs"
description: Learn about the MeasureBinding data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# MeasureBinding Data Type (ASSL)

  Defines a derived data type that represents the binding of a measure to the parent element.  
  
## Syntax  
  
```xml  
  
<MeasureBinding>  
   <!-- The following elements extend Binding -->  
   <MeasureID>...</MeasureID>  
</MeasureBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data type|[Binding](binding-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[MeasureID](../properties/measureid-element-assl.md)|  
|Derived elements|See [Binding](binding-data-type-assl.md)|  
  
## Remarks  
 For additional information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MeasureBinding>.  
  
  
