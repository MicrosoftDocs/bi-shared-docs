---
title: "Data Element (ASSL) | Microsoft Docs"
description: Learn about the Data object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Data Element (ASSL)

  Contains (in the collection of child [Block Element &#40;ASSL&#41;](../objects/block-element-assl.md) elements) the binary contents of a [ClrAssemblyFile](../data-type/clrassemblyfile-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<File xsi:type="ClrAssemblyFile">  
   ...  
   <Data xsi:type="DataBlock">...</Data>  
   ...  
</ClrAssemblyFile>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[DataBlock](../data-type/datablock-data-type-assl.md)|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[File](../objects/file-element-assl.md) of type [ClrAssemblyFile](../data-type/clrassemblyfile-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **Data** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ClrAssemblyFile>.  
  
## See Also  
 [Assembly Element &#40;ASSL&#41;](../objects/assembly-element-assl.md)   
 [ClrAssembly Data Type &#40;ASSL&#41;](../data-type/clrassembly-data-type-assl.md)   
 [Files Element &#40;ASSL&#41;](../collections/files-element-assl.md)   
 [Blocks Element &#40;ASSL&#41;](../collections/blocks-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  
