---
title: "OrderByAttributeID Element (ASSL) | Microsoft Docs"
description: Learn about the OrderByAttributeID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# OrderByAttributeID Element (ASSL)

  Identifies another attribute by which to order the members of the [Dimension](../data-type/dimensionattribute-data-type-assl.md) attribute.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute>  
   ...  
      <OrderByAttributeID>...</OrderByAttributeID>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **OrderByAttributeID** element is only used when the value of the [OrderBy](orderby-element-assl.md) element for the **DimensionAttribute** is set to *AttributeKey* or *AttributeName*.  
  
 The element that corresponds to the parent of **OrderByAttributeID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DimensionAttribute>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
