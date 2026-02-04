---
title: "MemberNamesUnique Element (ASSL) | Microsoft Docs"
description: Learn about the MemberNamesUnique property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# MemberNamesUnique Element (ASSL)

  Determines whether member names under the parent element must be unique.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute> <!-- or Hierarchy -->  
   ...  
   <MemberNamesUnique>   </MemberNamesUnique>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|False|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md),.[Hierarchy](../objects/hierarchy-element-assl.md)|  
|Child elements|None|  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
