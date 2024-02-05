---
title: "CaseCubeDimensionID Element (ASSL) | Microsoft Docs"
description: Learn about the CaseCubeDimensionID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# CaseCubeDimensionID Element (ASSL)

  Contains the identifier (ID) of the cube dimension that relates the data mining dimension to the measure group.  
  
## Syntax  
  
```xml  
  
<DataMiningMeasureGroupDimension>  
   ...  
   <CaseCubeDimensionID>...</CaseCubeDimensionID>  
   ...  
</DataMiningMeasureGroupDimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DataMiningMeasureGroupDimension](../data-type/dataminingmeasuregroupdimension-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **CaseCubeDimensionID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DataMiningMeasureGroupDimension>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
