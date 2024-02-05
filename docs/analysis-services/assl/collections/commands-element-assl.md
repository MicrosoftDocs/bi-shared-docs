---
title: "Commands Element (ASSL) | Microsoft Docs"
description: Learn about the Commands collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Commands Element (ASSL)

  Contains the collection of [Command](../objects/command-element-assl.md) elements associated with an [MdxScript](../objects/mdxscript-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MdxScript>  
   ...  
   <Commands>  
      <Command>...</Command>  
...</Commands>  
   ...  
</MdxScript>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[MdxScript](../objects/mdxscript-element-assl.md)|  
|Child elements|[Command](../objects/command-element-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CommandCollection>.  
