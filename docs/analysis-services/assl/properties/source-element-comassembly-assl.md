---
title: "Source Element (ComAssembly) (ASSL) | Microsoft Docs"
description: Learn about the Source COM assembly property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# Source Element (ComAssembly) (ASSL)

  Contains the file name or programmatic identifier (ProgID) for a Component Object Model (COM) component.  
  
## Syntax  
  
```xml  
  
<ComAssembly>  
   ...  
   <Source>...</Source>  
   ...  
</ComAssembly>  
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
|Parent element|[ComAssembly](../data-type/comassembly-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **Source** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ComAssembly>.  
  
## See Also  
 [Assembly Element &#40;ASSL&#41;](../objects/assembly-element-assl.md)   
 [ClrAssembly Data Type &#40;ASSL&#41;](../data-type/clrassembly-data-type-assl.md)   
 [Assemblies Element &#40;ASSL&#41;](../collections/assemblies-element-assl.md)   
 [Database Element &#40;ASSL&#41;](../objects/database-element-assl.md)   
 [Server Element &#40;ASSL&#41;](../objects/server-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
