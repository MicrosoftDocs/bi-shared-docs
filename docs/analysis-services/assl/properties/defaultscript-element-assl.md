---
title: "DefaultScript Element (ASSL) | Microsoft Docs"
description: Learn about the DefaultScript property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend

---
# DefaultScript Element (ASSL)

  Identifies the default [MdxScript](../objects/mdxscript-element-assl.md) element in the [MdxScripts](../collections/mdxscripts-element-assl.md) collection.  
  
## Syntax  
  
```xml  
  
<MdxScript>  
   ...  
   <DefaultScript>...</DefaultScript>  
   ...  
</MdxScript>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|**True**|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MdxScript](../objects/mdxscript-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 Setting the value of **DefaultScript** to **True** for one script sets the value of **DefaultScript** to **False** for all other **MdxScript** elements in the **MdxScripts** collection.  
  
 The element that corresponds to the parent of **DefaultScript** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MdxScript>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
