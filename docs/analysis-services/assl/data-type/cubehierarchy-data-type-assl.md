---
title: "CubeHierarchy Data Type (ASSL) | Microsoft Docs"
description: Learn about the CubeHierarchy data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# CubeHierarchy Data Type (ASSL)

  Defines a primitive data type that represents information about a [Hierarchy](../objects/hierarchy-element-assl.md) element in a [Cube](../objects/cube-element-assl.md) element.  
  
## Syntax  
  
```xml  
<CubeHierarchy>   <HierarchyID>...</HierarchyID>   <Name>...</Name>   <OptimizedState>...</OptimizedState>   <Visible>...</Visible>   <Enabled>...</Enabled>   <Annotations>...</Annotations></CubeHierarchy>  
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
|Child elements|[Annotations](../collections/annotations-element-assl.md), [Enabled](../properties/enabled-element-assl.md), [HierarchyID](../properties/hierarchyid-element-assl.md), [Name](../properties/name-element-assl.md), [OptimizedState](../properties/optimizedstate-element-assl.md), [Visible](../properties/visible-element-assl.md)|  
|Derived elements|[Hierarchy](../objects/hierarchy-element-assl.md) ([Hierarchies](../collections/hierarchies-element-assl.md) collection of [CubeDimension](cubedimension-data-type-assl.md))|  
  
## Remarks  
 This data type has no restrictions and can be used under any deployment mode: 0-Multidimensional and Data Mining, 1-SharePoint, and 2-Tabular.  
  
 In SQL Server 2016 Analysis Services and later, the *Enabled* property cannot be set to **False** for *CubeHierarchy*.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.CubeHierarchy>.  
  
## See Also  
 [Discover Method &#40;XMLA&#41;](../../xmla/xml-elements-methods-discover.md)   
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
