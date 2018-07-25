---
title: "DimensionID Element (ASSL) | Microsoft Docs"
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
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
|Parent elements|[CubeDimension](data-type/cubedimension-data-type-assl.md), [DimensionBinding](data-type/dimensionbinding-data-type-assl.md), [DimensionAttributeBinding](data-type/dimensionattributebinding-data-type-out-of-line-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **DimensionID** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CubeDimension> and <xref:Microsoft.AnalysisServices.DimensionBinding>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties/properties-assl.md)  
  
  
