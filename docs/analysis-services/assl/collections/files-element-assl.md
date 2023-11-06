---
title: "Files Element (ASSL) | Microsoft Docs"
description: Learn about the Files collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Files Element (ASSL)

  Contains the collection of [File](../objects/file-element-assl.md) elements that make up a [ClrAssembly](../data-type/clrassembly-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Assembly xsi:type="ClrAssembly">  
   ...  
   <Files>  
      <File xsi:type="ClrAssemblyFile">...</File>  
   </Files>  
   ...  
</Assembly>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Assembly](../objects/assembly-element-assl.md) of type [ClrAssembly](../data-type/clrassembly-data-type-assl.md)|  
|Child elements|[File](../objects/file-element-assl.md) of type [ClrAssemblyFile](../data-type/clrassemblyfile-data-type-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ClrAssemblyFileCollection>.  
