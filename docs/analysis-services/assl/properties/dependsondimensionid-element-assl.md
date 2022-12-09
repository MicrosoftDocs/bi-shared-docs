---
title: "DependsOnDimensionID Element (ASSL) | Microsoft Docs"
description: Learn about the DependsOnDimensionID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# DependsOnDimensionID Element (ASSL)

  Contains the identifier (ID) of another dimension on which the parent dimension depends.  
  
## Syntax  
  
```xml  
  
<Dimension>  
      ...  
   <DependsOnDimensionID>...</DependsOnDimensionID>  
   ...  
</Dimension>  
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
|Parent elements|[Dimension](../objects/dimension-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **DependsOnDimensionID** element is used by a dependent dimension to identify the dimension on which it depends.  
  
 The element that corresponds to the parent of **DependsOnDimensionID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Dimension>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
