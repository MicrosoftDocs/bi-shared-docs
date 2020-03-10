---
title: "OrderBy Element (ASSL) | Microsoft Docs"
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
# OrderBy Element (ASSL)

  Describes how to order the members contained in the attribute.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute>  
   ...  
      <OrderBy>...</OrderBy>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Name*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Name*|Order by the member name.|  
|*Key*|Order by the member key.|  
|*AttributeKey*|Order by the member key of the attribute specified in the [OrderByAttributeID](orderbyattributeid-element-assl.md) element of **DimensionAttribute**.|  
|*AttributeName*|Order by the member name of the attribute specified in the **OrderByAttributeID** element of **DimensionAttribute**.|  
  
 The enumeration that corresponds to the allowed values for **OrderBy** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.OrderBy>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
