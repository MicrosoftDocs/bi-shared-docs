---
title: "Invocation Element (ASSL) | Microsoft Docs"
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
# Invocation Element (ASSL)

  Specifies how an [Action](objects/action-element-assl.md) should be invoked.  
  
## Syntax  
  
```xml  
  
<Action>  
   ...  
   <Invocation>...</Invocation>  
   ...  
</Action>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Interactive*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Action](objects/action-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The invocation of an action depends on the client application. The **Invocation** element suggests to a client application how an action should be handled, and does not indicate to the instance of Analysis Services how to invoke an action.  
  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Interactive*|Invoked interactively by the user.|  
|*OnOpen*|Invoked when a client application opens the object.|  
|*Batch*|Invoked by a batch processing command.|  
  
 The enumeration that corresponds to the allowed values for **Invocation** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Action>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties/properties-assl.md)  
  
  
