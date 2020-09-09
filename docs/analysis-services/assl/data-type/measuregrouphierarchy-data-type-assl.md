---
title: "MeasureGroupHierarchy Data Type (ASSL) | Microsoft Docs"
description: Learn about the MeasureGroupHierarchy data type element in the Analysis Services Scripting Language (ASSL) schema.
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
# MeasureGroupHierarchy Data Type (ASSL)

  Defines a primitive data type that represents information about a hierarchy in a measure group.  
  
## Syntax  
  
```xml  
  
<MeasureGroupHierarchy>  
   <HierarchyID>...</HierarchyID>  
      <Annotations>...</Annotations>  
</MeasureGroupHierarchy>  
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
|Child elements|[Annotations](../collections/annotations-element-assl.md), [HierarchyID](../properties/hierarchyid-element-assl.md)|  
|Derived elements|[Hierarchy](../objects/hierarchy-element-assl.md) ([Hierarchies](../collections/hierarchies-element-assl.md) collection of [RegularMeasureGroupDimension](regularmeasuregroupdimension-data-type-assl.md))|  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
