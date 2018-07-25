---
title: "ActionID Element (ASSL) | Microsoft Docs"
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# ActionID Element (ASSL)

  Contains the name of an [Action](../objects/action-element-assl.md) element defined on a [Cube](../objects/cube-element-assl.md) element that is made available in a [Perspective](../objects/perspective-element-assl.md) element as a [PerspectiveAction](../data-type/perspectiveaction-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<PerspectiveAction>  
   <ActionID>...</ActionID  
</PerspectiveAction>  
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
|Parent elements|[PerspectiveAction](../data-type/perspectiveaction-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **ActionID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.PerspectiveAction>.  
  
## See Also  
 [Actions Element &#40;ASSL&#41;](collections/actions-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
