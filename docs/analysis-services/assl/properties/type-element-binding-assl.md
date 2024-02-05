---
title: "Type Element (Binding) (ASSL) | Microsoft Docs"
description: Learn about the Type property element for Binding in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# Type Element (Binding) (ASSL)

  Contains the type of the attribute binding.  
  
## Syntax  
  
```xml  
  
<AttributeBinding> <!-- or CubeAttributeBinding -->  
   ...  
   <Type>...</Type>  
   ...  
</AttributeBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[AttributeBinding](../data-type/attributebinding-data-type-assl.md), [CubeAttributeBinding](../data-type/cubeattributebinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*All*|All level|  
|*Key*|Member keys|  
|*Name*|Member name|  
|*Value*|Member value|  
|*Translation*|Member translations|  
|*UnaryOperator*|Unary operators|  
|*SkippedLevels*|Skipped levels|  
|*CustomRollup*|Custom rollup formulas|  
|*CustomRollupProperties*|Custom rollup properties|  
  
 The elements that correspond to the parents of **Type** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.AttributeBinding> and <xref:Microsoft.AnalysisServices.CubeAttributeBinding>.  
  
## See Also  
 [Binding Data Type &#40;ASSL&#41;](../data-type/binding-data-type-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
