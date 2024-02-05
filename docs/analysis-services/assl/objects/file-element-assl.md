---
title: "File Element (ASSL) | Microsoft Docs"
description: Learn about the File object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# File Element (ASSL)

  Defines one of the files that compose a Microsoft .NET Framework[ClrAssembly](../data-type/clrassembly-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Files>  
   <File xsi:type="ClrAssemblyFile">...</File>  
</Files>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[ClrAssemblyFile](../data-type/clrassemblyfile-data-type-assl.md)|  
|Default value|None|  
|Cardinality|1-n: Required element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Files](../collections/files-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **Files** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ClrAssemblyFile>.  
  
## See Also  
 [Server Element &#40;ASSL&#41;](../objects/server-element-assl.md)   
 [Database Element &#40;ASSL&#41;](../objects/database-element-assl.md)   
 [Assemblies Element &#40;ASSL&#41;](../collections/assemblies-element-assl.md)   
 [Assembly Element &#40;ASSL&#41;](../objects/assembly-element-assl.md)   
 [ClrAssembly Data Type &#40;ASSL&#41;](../data-type/clrassembly-data-type-assl.md)   
 [Data Element &#40;ASSL&#41;](../objects/data-element-assl.md)   
 [DataBlock Data Type &#40;ASSL&#41;](../data-type/datablock-data-type-assl.md)   
 [Blocks Element &#40;ASSL&#41;](../collections/blocks-element-assl.md)   
 [Block Element &#40;ASSL&#41;](../objects/block-element-assl.md)   
 [ComAssembly Data Type &#40;ASSL&#41;](../data-type/comassembly-data-type-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  
