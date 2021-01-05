---
title: "LName Element (XMLA) | Microsoft Docs"
description: Learn how the LName element contains information about unique level names for the parent HierarchyInfo or Member element.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# LName Element (XMLA)

  Contains information about unique level names for the parent [HierarchyInfo](../xml-elements-properties/hierarchyinfo-element-xmla.md) or [Member](../xml-elements-properties/member-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<HierarchyInfo> <!-- or Member -->  
   ...  
   <LName>...</LName>  
   ...  
</HierarchyInfo>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[HierarchyInfo](../xml-elements-properties/hierarchyinfo-element-xmla.md), [Member](../xml-elements-properties/member-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 For **HierarchyInfo** elements, this element contains the name of the property that provides the unique level names of the hierarchy. The value is equivalent to the LEVEL_UNIQUE_NAME property defined for axis rowsets in the OLE DB for OLAP specification.  
  
 For **Member** elements, this element contains the unique name of the level in the hierarchy that contains the member represented by the parent **Member** element.  
