---
title: "New Element (XMLA) | Microsoft Docs"
description: Learn how the New element contains the new file system storage location used by a Folder element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# New Element (XMLA)

  Contains the new file system storage location used by a [Folder](../xml-elements-properties/folder-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Folder>  
   ...  
   <New>...</New>  
   ...  
</Folder>  
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
|Parent elements|[Folder](../xml-elements-properties/folder-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **New** element contains a UNC path that replaces the value of the **Original** element contained by the parent **Folder** element for all objects restored or synchronized, respectively, during a **Restore** or **Synchronize** command. The value of the **Original** element is compared to the value of the **StorageLocation** element for each cube, measure group, or partition and, if a match is found, the value of this element is used to update the **StorageLocation** of the object during restoration or synchronization.  