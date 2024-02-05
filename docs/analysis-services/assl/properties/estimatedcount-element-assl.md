---
title: "EstimatedCount Element (ASSL) | Microsoft Docs"
description: Learn about the EstimatedCount property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# EstimatedCount Element (ASSL)

  Contains the estimated number of members for an attribute, as defined by the user.  
  
## Syntax  
  
```xml  
  
<AggregationDesignAttribute> <!-- or DimensionAttribute -->  
      ...  
   <EstimatedCount>...</EstimatedCount>  
   ...  
</AggregationDesignAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Long|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[AggregationDesignAttribute](../data-type/aggregationdesignattribute-data-type-assl.md), [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 This value is assigned by the user and is used by the [AggregationDesign Element &#40;ASSL&#41;](../objects/aggregationdesign-element-assl.md).  
  
 The elements that correspond to the parents of **EstimatedCount** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.AggregationDesignAttribute> and <xref:Microsoft.AnalysisServices.DimensionAttribute>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
