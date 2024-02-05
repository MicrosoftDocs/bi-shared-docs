---
title: "Text Element (ASSL) | Microsoft Docs"
description: Learn about the Text property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# Text Element (ASSL)

  Contains the text of a [Command](../objects/command-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Text>...</Text>  
</Command>  
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
|Parent element|[Command](../objects/command-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **Text** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Command>.  
  
## See Also  
 [Commands Element &#40;ASSL&#41;](../collections/commands-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
