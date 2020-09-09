---
title: "Relationships Element (ASSL) | Microsoft Docs"
description: Learn about the Relationships collection element in the Analysis Services Scripting Language (ASSL) schema.
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
# Relationships Element (ASSL)

  Contains the collection of relationships for the associated dimension.  
  
## Syntax  
  
```xml  
  
<CubeDimension> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Attributes>  
      <Attribute>...</Attribute>  
  </Attributes>  
   ...  
</CubeDimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[CubeDimension](../data-type/cubedimension-data-type-assl.md), [Dimension](../objects/dimension-element-assl.md), [PerspectiveDimension](../data-type/perspectivedimension-data-type-assl.md), [RegularMeasureGroupDimension](../data-type/regularmeasuregroupdimension-data-type-assl.md)|  
|Child elements|[Relationship](../data-type/relationship-data-type-assl.md)|  
  
## Remarks  
 The corresponding elements in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.RelationshipCollection>.  
