---
title: "Expression Element (ASSL) | Microsoft Docs"
description: Learn about the Expression property element in the Analysis Services Scripting Language (ASSL) schema.
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
# Expression Element (ASSL)

  Contains a Multidimensional Expressions (MDX) expression that defines the contents of the parent element.  
  
## Syntax  
  
```xml  
  
<CellPermission> <!-- or StandardAction -->  
   ...  
   <Expression>...</Expression>  
   ...  
</CellPermission>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CellPermission](../objects/cellpermission-element-assl.md), [StandardAction](../data-type/standardaction-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 For the **CellPermission** element, the **Expression** element contains a logical MDX expression that identifies cells applicable to the rights indicated by the [Access](access-element-assl.md) element of the **CellPermission** element. If the value of an **Expression** element for a **CellPermission** element is empty, the **CellPermission** element is ignored.  
  
 For the **StandardAction** element, the **Expression** element contains an MDX expression that represents the contents of the action. If the value of an **Expression** element for a **StandardAction** element is empty, the **StandardAction** element is ignored.  
  
 The elements that correspond to the parents in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CellPermission> and <xref:Microsoft.AnalysisServices.StandardAction>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
