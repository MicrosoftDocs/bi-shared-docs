---
title: "Original Element (XMLA) | Microsoft Docs"
description: Learn how the Original element contains the original file system storage location used by a Folder element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Original Element (XMLA)

  Contains the original file system storage location used by a [Folder](../xml-elements-properties/folder-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Folder>  
   ...  
   <Original>...</Original>  
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
 The **Original** element contains a UNC path to be replaced with the value of the [New](../xml-elements-properties/new-element-xmla.md) element contained by the parent **Folder** element for all objects restored or synchronized, respectively, during a [Restore](../xml-elements-commands/restore-element-xmla.md) or [Synchronize](../xml-elements-commands/synchronize-element-xmla.md) command. The value of this element is compared to the value of the [StorageLocation](../../assl/properties/storagelocation-element-assl.md) element for each cube, measure group, or partition and, if a match is found, the value of the **New** element is used to update the **StorageLocation** of the object during restoration or synchronization.  
