---
title: "Folder Element (XMLA) | Microsoft Docs"
description: Learn how the Folder element contains a file system storage location to be updated for a Location element during a Restore or Synchronize command.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Folder Element (XMLA)

  Contains a file system storage location to be updated for a [Location](../xml-elements-properties/location-element-xmla.md) element during a [Restore](../xml-elements-commands/restore-element-xmla.md) or [Synchronize](../xml-elements-commands/synchronize-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<Folders>  
   ...  
   <Folder>  
      <Original>...</Original>  
      <New>...</New>  
   </Folder>  
   ...  
</Folders>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Folders](../xml-elements-properties/folders-element-xmla.md)|  
|Child elements|[New](../xml-elements-properties/new-element-xmla.md), [Original](../xml-elements-properties/original-element-xmla.md)|  
  
## Remarks  
 The **Folder** element, if specified, changes the storage locations of objects contained either by the backup file (for **Restore** commands) or the database on the source instance (for **Synchronize** commands) that match the value of the **Original** element to the value of the **New** element.