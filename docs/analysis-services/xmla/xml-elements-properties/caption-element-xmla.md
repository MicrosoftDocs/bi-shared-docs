---
title: "Caption Element (XMLA) | Microsoft Docs"
description: Learn how the Caption element contains information about the caption of the parent HierarchyInfo or Member element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Caption Element (XMLA)

  Contains information about the caption of the parent [HierarchyInfo](../xml-elements-properties/hierarchyinfo-element-xmla.md) or [Member](../xml-elements-properties/member-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<HierarchyInfo> <!-- or Member -->  
   ...  
   <Caption>...</Caption>  
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
 For **HierarchyInfo** elements, the **Caption** element contains the name of the property that provides the member captions of the hierarchy. The value is equivalent to the MEMBER_CAPTION property defined for axis rowsets in the OLE DB for OLAP specification.  
  
 For **Member** elements, the **Caption** element contains the caption of the parent **Member** element in the language specified for the XML for Analysis (XMLA) session. If no caption is available, this element contains the unique name of the member.  
  
