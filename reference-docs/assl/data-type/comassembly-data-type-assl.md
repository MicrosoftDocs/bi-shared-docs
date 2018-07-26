---
title: "ComAssembly Data Type (ASSL) | Microsoft Docs"
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
# ComAssembly Data Type (ASSL)

  Defines a derived data type that represents a COM library associated with a [Server](../objects/server-element-assl.md) or [Database](../objects/database-element-assl.md) element.  
  
> [!IMPORTANT]  
>  COM assemblies might pose a security risk. Due to this risk and other considerations, COM assemblies are depreceated.
  
## Syntax  
  
```xml  
  
<ComAssembly>  
      <!-- The following elements extend Assembly -->  
   <Source>...</Source>  
</ComAssembly>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Assembly](../objects/assembly-element-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Source](../properties/source-element-comassembly-assl.md)|  
|Derived elements|See [Assembly](../objects/assembly-element-assl.md) ([Assemblies](../collections/assemblies-element-assl.md) collection of [Database](../objects/database-element-assl.md) or [Server](../objects/server-element-assl.md))|  
  
## Remarks  
 The **ComAssembly** element contains a reference (either the fully qualified file name or the programmatic identifier) to a COM library associated with an instance of Analysis Services or with a specific database on an instance.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ComAssembly>.  
  
## See Also  
 [ClrAssembly Data Type &#40;ASSL&#41;](clrassembly-data-type-assl.md)   
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
