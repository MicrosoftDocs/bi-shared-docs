---
title: "DisplayInfo Element (XMLA) | Microsoft Docs"
description: Learn how the DisplayInfo element contains display information for the parent HierarchyInfo or Member element. 
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# DisplayInfo Element (XMLA)

  Contains display information for the parent [HierarchyInfo](../xml-elements-properties/hierarchyinfo-element-xmla.md) or [Member](../xml-elements-properties/member-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<HierarchyInfo> <!-- or Member -->  
   ...  
   <DisplayInfo>...</DisplayInfo>  
   ...  
</HierarchyInfo>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|unsignedInt|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[HierarchyInfo](../xml-elements-properties/hierarchyinfo-element-xmla.md), [Member](../xml-elements-properties/member-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **DisplayInfo** element contains various items of information that help a client application render the parent **HierarchyInfo** or **Member** element. The value is equivalent to the DISPLAY_INFO property defined for axis rowsets in the OLE DB for OLAP specification.  

