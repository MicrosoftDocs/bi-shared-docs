---
title: "MdxMissingMemberMode Element (ASSL) | Microsoft Docs"
description: Learn about the MdxMissingMemberMode property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# MdxMissingMemberMode Element (ASSL)

  Determines how missing members are handled for Multidimensional Expressions (MDX) statements.  
  
## Syntax  
  
```xml  
  
<Dimension>  
   ...  
   <MdxMissingMemberMode>...</MdxMissingMemberMode>  
   ...  
</Dimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Default*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Dimension](../data-type/dimension-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Ignore*|Missing members are ignored.|  
|*Error*|An error is raised if missing members are encountered.|  
|*Default*|Missing members are ignored.|  
  
 The element that corresponds to the parent of **MdxMissingMemberMode** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Dimension>.  

  
  
