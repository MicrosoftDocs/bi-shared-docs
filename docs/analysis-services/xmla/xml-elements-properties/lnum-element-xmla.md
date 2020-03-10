---
title: "LNum Element (XMLA) | Microsoft Docs"
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# LNum Element (XMLA)

  Contains information about level ordinal positions for the parent [HierarchyInfo](../xml-elements-properties/hierarchyinfo-element-xmla.md) or [Member](../xml-elements-properties/member-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<HierarchyInfo> <!-- or Member -->  
   ...  
   <LNum>...</LNum>  
   ...  
</HierarchyInfo>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|int|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[HierarchyInfo](../xml-elements-properties/hierarchyinfo-element-xmla.md), [Member](../xml-elements-properties/member-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 For **HierarchyInfo** elements, the **LNum** element contains the name of the property that provides the level ordinal positions of the hierarchy. The value is equivalent to the LEVEL_NUMBER property defined for axis rowsets in the OLE DB for OLAP specification.  
  
 For **Member** elements, the **LNum** element contains the zero-based ordinal position, from the root level of the hierarchy, of the member represented by the parent [Member](../xml-elements-properties/member-element-xmla.md) element. A value of zero represents the root level of the hierarchy.  
 