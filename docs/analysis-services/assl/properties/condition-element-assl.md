---
title: "Condition Element (ASSL) | Microsoft Docs"
description: Learn about the Condition property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Condition Element (ASSL)

  Contains a Multidimensional Expressions (MDX) expression that determines whether the [Action](../objects/action-element-assl.md) parent element applies to the target.  
  
## Syntax  
  
```xml  
  
<Action>  
   ...  
   <Condition>...</Condition  
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
|Parent element|[Action](../objects/action-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **Condition** element contains an MDX expression that evaluates to a Boolean value. If the expression returns **True**, then the **Action** applies to the target specified in the [Target](target-element-assl.md) element. Otherwise, the **Action** is not applicable.  
  
 The element that corresponds to the parent of **Condition** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Action>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
