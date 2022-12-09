---
title: "Source Element (Measure) (ASSL) | Microsoft Docs"
description: Learn about the Source measure property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# Source Element (Measure) (ASSL)

  Contains the details of the source containing the value of the [Measure](../objects/measure-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Measure>  
      ...  
   <Source xsi:type="DataItem">...</Source>  
      ...  
</Measure>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Measure](../objects/measure-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **Source** of the **DataItem**, which serves as the **Source** of the **Measure**, can in turn be of type [RowBinding](../data-type/rowbinding-data-type-assl.md), [ColumnBinding](../data-type/columnbinding-data-type-assl.md), [MeasureBinding](../data-type/measurebinding-data-type-assl.md), or [CubeDimensionBinding](../data-type/cubedimensionbinding-data-type-assl.md).  
  
 For additional information about the **DataItem** type, including a table of ASSL objects and properties of the **DataItem** type, see [DataItem Data Type &#40;ASSL&#41;](../data-type/dataitem-data-type-assl.md).  
  
 The element corresponding to the parent of **Source** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Measure>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
