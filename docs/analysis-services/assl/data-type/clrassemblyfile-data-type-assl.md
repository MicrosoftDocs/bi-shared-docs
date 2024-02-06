---
title: "ClrAssemblyFile Data Type (ASSL) | Microsoft Docs"
description: Learn about the ClrAssemblyFile data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# ClrAssemblyFile Data Type (ASSL)

  Defines a primitive data type that represents one of the files that compose a Microsoft .NET Framework**Assembly** ([ClrAssembly](clrassembly-data-type-assl.md) element).  
  
## Syntax  
  
```xml  
  
<ClrAssemblyFile>  
   <Name>...</Name>  
      <Type>...</Type>  
      <Data>...</Data>  
</ClrAssemblyFile>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Data](../objects/data-element-assl.md), [Name](../properties/name-element-assl.md), [Type](../properties/type-element-clrassemblyfile-assl.md)|  
|Derived elements|[File](../objects/file-element-assl.md) ([Files](../collections/files-element-assl.md) collection of [ClrAssembly](clrassembly-data-type-assl.md))|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ClrAssemblyFile>.  
  
## See Also  
 [Server Element &#40;ASSL&#41;](../objects/server-element-assl.md)   
 [Database Element &#40;ASSL&#41;](../objects/database-element-assl.md)   
 [Assemblies Element &#40;ASSL&#41;](../collections/assemblies-element-assl.md)   
 [Assembly Element &#40;ASSL&#41;](../objects/assembly-element-assl.md)   
 [DataBlock Data Type &#40;ASSL&#41;](datablock-data-type-assl.md)   
 [Blocks Element &#40;ASSL&#41;](../collections/blocks-element-assl.md)   
 [Block Element &#40;ASSL&#41;](../objects/block-element-assl.md)   
 [ComAssembly Data Type &#40;ASSL&#41;](comassembly-data-type-assl.md)   
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
