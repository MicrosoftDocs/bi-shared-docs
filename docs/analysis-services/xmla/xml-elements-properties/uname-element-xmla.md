---
title: "UName Element (XMLA) | Microsoft Docs"
description: Learn how the UName element contains the unique name of the parent HierarchyInfo or Member element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# UName Element (XMLA)

  Contains the unique name of the parent [HierarchyInfo](../xml-elements-properties/hierarchyinfo-element-xmla.md) or [Member](../xml-elements-properties/member-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<HierarchyInfo> <!-- or Member -->  
   ...  
   <UName>...</UName>  
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
 For **HierarchyInfo** elements, the **UName** element contains the name of the property that provides the unique member names of the hierarchy. The value is equivalent to the MEMBER_UNIQUE_NAME property defined for axis rowsets in the OLE DB for OLAP specification.  
  
 For **Member** elements, the **UName** element contains the unique name of the parent **Member** element.  
