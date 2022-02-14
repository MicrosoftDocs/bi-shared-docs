---
title: "AggregationUsage Element (ASSL) | Microsoft Docs"
description: Learn about the AggregationUsage property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AggregationUsage Element (ASSL)

  Controls how the Aggregation Designer in Analysis Services designs aggregations.  
  
## Syntax  
  
```xml  
  
<CubeAttribute>  
   ...  
   <AggregationUsage>...</AggregationUsage>  
   ...  
</CubeAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Default*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[CubeAttribute](../data-type/cubeattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Full*|Every aggregation for the cube must include this attribute.|  
|*None*|No aggregation for the cube should include this attribute.|  
|*Unrestricted*|No restrictions are placed on the Aggregation Designer.|  
|*Default*|The Aggregation Designer applies a default rule based on the type of attribute (*Full* for keys, *Unrestricted* for others).|  
  
 The enumeration that corresponds to the allowed values for **AggregationUsage** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.AggregationUsage>.  
  
## See Also  
 [Cube Element &#40;ASSL&#41;](../objects/cube-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
