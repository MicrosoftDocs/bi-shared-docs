---
title: "ClrAssembly Data Type (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# ClrAssembly Data Type (ASSL)

  Defines a derived data type that represents a  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assembly associated with a [Database](objects/database-element-assl.md) or [Server](objects/server-element-assl.md) element  
  
## Syntax  
  
```xml  
  
<ClrAssembly>  
      <!-- The following elements extend Assembly -->  
   <Files>...</Files>  
      <PermissionSet>...</PermissionSet>  
</ClrAssembly>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Assembly](objects/assembly-element-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None (abstract type)|  
|Child elements|[Files](collections/files-element-assl.md), [PermissionSet](properties/permissionset-element-assl.md)|  
|Derived elements|See [Assembly](objects/assembly-element-assl.md) ([Assemblies](collections/assemblies-element-assl.md) collection of [Database](objects/database-element-assl.md) or [Server](objects/server-element-assl.md))|  
  
## Remarks  
 The **ClrAssembly** element contains the files needed to recreate a [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assembly, associated either with an instance of Analysis Services or with a specific database on an instance of [!INCLUDE[ssAS](../../../includes/ssas-md.md)], as well as the permissions needed to execute the assembly.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ClrAssembly>.  
  
## See Also  
 [File Element &#40;ASSL&#41;](objects/file-element-assl.md)   
 [ClrAssemblyFile Data Type &#40;ASSL&#41;](data-type/clrassemblyfile-data-type-assl.md)   
 [Data Element &#40;ASSL&#41;](objects/data-element-assl.md)   
 [DataBlock Data Type &#40;ASSL&#41;](data-type/datablock-data-type-assl.md)   
 [Blocks Element &#40;ASSL&#41;](collections/blocks-element-assl.md)   
 [Block Element &#40;ASSL&#41;](objects/block-element-assl.md)   
 [ComAssembly Data Type &#40;ASSL&#41;](data-type/comassembly-data-type-assl.md)   
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
