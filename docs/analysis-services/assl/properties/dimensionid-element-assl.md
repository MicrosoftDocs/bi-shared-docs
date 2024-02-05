---
title: "DimensionID Element (ASSL) | Microsoft Docs"
description: Learn about the DimensionID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# DimensionID Element (ASSL)

  Contains the identifier (ID) of the dimension.  
  
## Syntax  
  
```xml  
  
<CubeDimension> <!-- or DimensionBinding, DimensionAttributeBinding -- >  
   ...  
   <DimensionID>...</DimensionID>  
      ...  
</CubeDimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CubeDimension](../data-type/cubedimension-data-type-assl.md), [DimensionBinding](../data-type/dimensionbinding-data-type-assl.md), [DimensionAttributeBinding](../data-type/dimensionattributebinding-data-type-out-of-line-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **DimensionID** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CubeDimension> and <xref:Microsoft.AnalysisServices.DimensionBinding>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
