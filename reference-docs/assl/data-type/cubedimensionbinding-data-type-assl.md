---
title: "CubeDimensionBinding Data Type (ASSL) | Microsoft Docs"
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
# CubeDimensionBinding Data Type (ASSL)

  Defines a derived data type that represents the binding of a [Dimension](objects/dimension-element-assl.md), [Measure](objects/measure-element-assl.md), or [MiningModel](objects/miningmodel-element-assl.md) element to a cube dimension.  
  
## Syntax  
  
```xml  
  
<CubeDimensionBinding>  
      <!-- The following elements extend Binding -->  
   <DataSourceID>...</DataSourceID>  
   <CubeID>...</CubeID>  
   <CubeDimensionID>...</CubeDimensionID>  
   <Filter>...</Filter>  
</CubeDimensionBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Binding](binding-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[CubeDimensionID](properties/cubedimensionid-element-assl.md), [CubeID](properties/cubeid-element-assl.md), [DataSourceID](properties/datasourceid-element-assl.md), [Filter](properties/filter-element-trace-assl.md)|  
|Derived elements|See [Binding](binding-data-type-assl.md)|  
  
## Remarks  
 For additional information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md).  
  
 For an overview of data bindings in ASSL, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CubeDimensionBinding>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
