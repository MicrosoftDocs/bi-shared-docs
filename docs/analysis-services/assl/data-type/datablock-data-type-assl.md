---
title: "DataBlock Data Type (ASSL) | Microsoft Docs"
description: Learn about the DataBlock data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# DataBlock Data Type (ASSL)

  Defines a primitive data type that represents a collection of data blocks used to store the binary contents of a [ClrAssemblyFile](clrassemblyfile-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<DataBlock>  
   <Blocks>...</Blocks>  
</DataBlock>  
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
|Child elements|[Blocks](../collections/blocks-element-assl.md)|  
|Derived elements|[Data](../objects/data-element-assl.md) element of [ClrAssemblyFile](clrassemblyfile-data-type-assl.md) type ([Files](../collections/files-element-assl.md) collection of [ClrAssembly](clrassembly-data-type-assl.md) type)|  
  
## See Also  
 [Assembly Element &#40;ASSL&#41;](../objects/assembly-element-assl.md)   
 [File Element &#40;ASSL&#41;](../objects/file-element-assl.md)   
 [Block Element &#40;ASSL&#41;](../objects/block-element-assl.md)   
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
