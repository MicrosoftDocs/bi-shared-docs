---
title: "PerspectiveHierarchy Data Type (ASSL) | Microsoft Docs"
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
# PerspectiveHierarchy Data Type (ASSL)

  Defines a primitive data type that represents information about a hierarchy in a [PerspectiveDimension](perspectivedimension-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<PerspectiveHierarchy>  
   <HierarchyID>...</HierarchyID>  
      <Annotations>...</Annotations>  
</PerspectiveHierarchy>  
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
|Child elements|[Annotations](collections/annotations-element-assl.md), [HierarchyID](properties/hierarchyid-element-assl.md)|  
|Derived elements|[Hierarchy](objects/hierarchy-element-assl.md) ([Hierarchies](collections/hierarchies-element-assl.md) collection of [PerspectiveDimension](perspectivedimension-data-type-assl.md))|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.PerspectiveHierarchy>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
