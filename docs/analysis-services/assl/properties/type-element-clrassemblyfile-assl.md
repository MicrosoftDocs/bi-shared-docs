---
title: "Type Element (ClrAssemblyFile) (ASSL) | Microsoft Docs"
description: Learn about the Type property element for CLR assembly file in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend

---
# Type Element (ClrAssemblyFile) (ASSL)

  Specifies the file type of one of the files that belong to a  .NET Framework assembly.  
  
## Syntax  
  
```xml  
  
<ClrAssemblyFile>  
      ...  
      <Type>...</Type>  
   ...  
</ClrAssemblyFile>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ClrAssemblyFile](../data-type/clrassemblyfile-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the following strings:  
  
|Value|Description|  
|-----------|-----------------|  
|*Main*|Specified file is the main file in the assembly.|  
|*Dependent*|Specified file is a dependent file in the assembly.|  
|*Debug*|Specified file contains debugging information.|  
  
 The enumeration that corresponds to the allowed values for **Type** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ClrAssemblyFileType>.  
  
 The element that corresponds to the parent of **Type** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ClrAssemblyFile>.  
  
## See Also  
 [File Element &#40;ASSL&#41;](../objects/file-element-assl.md)   
 [Files Element &#40;ASSL&#41;](../collections/files-element-assl.md)   
 [ClrAssembly Data Type &#40;ASSL&#41;](../data-type/clrassembly-data-type-assl.md)   
 [Assembly Element &#40;ASSL&#41;](../objects/assembly-element-assl.md)   
 [Assemblies Element &#40;ASSL&#41;](../collections/assemblies-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
