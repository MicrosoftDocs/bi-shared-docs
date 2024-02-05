---
title: "AllMemberAggregationUsage Element (ASSL) | Microsoft Docs"
description: Learn about the AllMemberAggregationUsage property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 09/14/2020
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# AllMemberAggregationUsage Element (ASSL)

  Controls how the Aggregation Designer in Analysis Services designs aggregations.  
  
## Syntax  
  
```xml  
  
<CubeDimension>  
   ...  
   <AllMemberAggregationUsage>...</AllMemberAggregationUsage>  
   ...  
</CubeDimension>  
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
|Parent elements|[CubeDimension](../data-type/cubedimension-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks

 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Full*|Every aggregation for the cube must include the All member.|  
|*None*|No aggregation for the cube should include the All member.|  
|*Unrestricted*|No restrictions are placed on the Aggregation Designer.|  
|*Default*|Same as *Unrestricted*.|  
  
 The element that corresponds to the parent of **AllMemberAggregationUsage** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CubeDimension>.  
  
## See Also

 [Cube Element &#40;ASSL&#41;](../objects/cube-element-assl.md)   
 [Dimension Element &#40;ASSL&#41;](../objects/dimension-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
