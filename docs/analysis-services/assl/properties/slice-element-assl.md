---
title: "Slice Element (ASSL) | Microsoft Docs"
description: Learn about the Slice property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# Slice Element (ASSL)

  Contains a Multidimensional Expressions (MDX) expression defining the slice contained in a partition.  
  
## Syntax  
  
```xml  
  
<Partition>  
      ...  
   <Slice>...</Slice>  
   ...  
</Partition>  
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
|Parent element|[Partition](../objects/partition-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **Slice** element contains an MDX tuple expression or set expression that identifies the portion of the cube for which the partition stores information. The MDX expression is similar to the StrToSet MDX function with the CONSTRAINED keyword, in that the expression cannot include MDX or user-defined functions.  
  
 The element that corresponds to the parent of **Slice** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Partition>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
