---
title: "AttributeHierarchyVisible Element (ASSL) | Microsoft Docs"
description: Learn about the AttributeHierarchyVisible property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# AttributeHierarchyVisible Element (ASSL)

  Determines whether the attribute hierarchy is visible to client applications.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute> <!-- or CubeAttribute or PerspectiveAttribute -->  
   ...  
   <AttributeHierarchyVisible>...</AttributeHierarchyVisible>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|**True**|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[CubeAttribute](../data-type/cubeattribute-data-type-assl.md), [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md), [PerspectiveAttribute](../data-type/perspectiveattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **AttributeHierarchyVisible** element determines whether the attribute hierarchy associated with the attribute is visible to client applications. If this element is set to **False**, the attribute hierarchy can still be used to create user-defined hierarchies and can be referenced by Multidimensional Expressions (MDX) statements.  
  
 The elements that correspond to the parents of **AttributeHierarchyVisible** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CubeAttribute>, <xref:Microsoft.AnalysisServices.DimensionAttribute>, and <xref:Microsoft.AnalysisServices.PerspectiveAttribute>.  
  
## See Also  
 [AttributeHierarchyEnabled Element &#40;ASSL&#41;](attributehierarchyenabled-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
