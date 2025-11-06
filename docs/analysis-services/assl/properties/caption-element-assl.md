---
title: "Caption Element (ASSL) | Microsoft Docs"
description: Learn about the Caption property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# Caption Element (ASSL)

  Contains the caption for the associated parent element.  
  
## Syntax  
  
```xml  
  
<Action> <!-- or Translation -->  
   ...  
  <Caption>...</Caption>  
   ...  
</Action>  
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
|Parent element|[Action](../objects/action-element-assl.md), [Translation](../objects/translation-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **Caption** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.Action> and <xref:Microsoft.AnalysisServices.Translation>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
