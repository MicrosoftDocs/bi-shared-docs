---
title: "Folders Element (XMLA) | Microsoft Docs"
description: Learn how the Folders element contains a collection of Folder elements used by the parent Location element during a Restore or Synchronize command.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Folders Element (XMLA)

  Contains a collection of [Folder](../xml-elements-properties/folder-element-xmla.md) elements used by the parent [Location](../xml-elements-properties/location-element-xmla.md) element during a [Restore](../xml-elements-commands/restore-element-xmla.md) or [Synchronize](../xml-elements-commands/synchronize-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<Location>  
   ...  
   <Folders>  
      <Folder>...</Folder>  
   </Folders>  
   ...  
</Location>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None (collection)|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Location](../xml-elements-properties/location-element-xmla.md)|  
|Child elements|[Folder](../xml-elements-properties/folder-element-xmla.md)|  
  
## Remarks  
