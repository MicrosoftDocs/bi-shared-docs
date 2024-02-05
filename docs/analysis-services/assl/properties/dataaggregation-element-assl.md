---
title: "DataAggregation Element (ASSL) | Microsoft Docs"
description: Learn about the DataAggregation property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/25/2018
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# DataAggregation Element (ASSL)

  Determines whether the instance can aggregate persisted data or cached data for the [MeasureGroup](../objects/measuregroup-element-assl.md).  
  
> [!IMPORTANT]
> Do not modify this property. This property is currently ignored by the engine. 
  
## Syntax  
  
```xml  
  
<MeasureGroup>  
   ...  
   <DataAggregation>...</DataAggregation>  
   ...  
</MeasureGroup>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*DataAndCacheAggregatable*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MeasureGroup](../objects/measuregroup-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*None*|Aggregation is not performed for this measure group.|  
|*DataAggregatable*|Persisted data is aggregatable for this measure group.|  
|*CacheAggregatable*|Cached data is aggregatable for this measure group.|  
|*DataAndCacheAggregatable*|Both persisted data and cached data are aggregatable for this measure group.|  
  
 The element that corresponds to the parent of **DataAggregation** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MeasureGroup>.  
  
## See Also  
 [Cube Element &#40;ASSL&#41;](../objects/cube-element-assl.md)   
 [Dimension Element &#40;ASSL&#41;](../objects/dimension-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
