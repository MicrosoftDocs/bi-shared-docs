---
title: "ManyToManyMeasureGroupDimension Data Type (ASSL) | Microsoft Docs"
description: Learn about the ManyToManyMeasureGroupDimension data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# ManyToManyMeasureGroupDimension Data Type (ASSL)

  Defines a derived data type that represents the relationship between a many-to-many dimension and a measure group.  
  
## Syntax  
  
```xml  
  
<ManyToManyMeasureGroupDimension>  
   <!-- The following elements extend MeasureGroupDimension -->  
   <MeasureGroupID>...</MeasureGroupID>  
   <DefaultMember>...</DefaultMember>  
</ManyToManyMeasureGroupDimension>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[MeasureGroupDimension](measuregroupdimension-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[DefaultMember](../properties/defaultmember-element-assl.md), [MeasureGroupID](../properties/measuregroupid-element-assl.md)|  
|Derived elements|None|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ManyToManyMeasureGroupDimension>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
