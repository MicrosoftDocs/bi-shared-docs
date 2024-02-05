---
title: "DataSourceID Element (XMLA) | Microsoft Docs"
description: Learn how the DataSourceID element identifies a data source used by a Location element during a Backup, Restore, or Synchronize command. 
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# DataSourceID Element (XMLA)

  Identifies a data source used by a [Location](../xml-elements-properties/location-element-xmla.md) element during a [Backup](../xml-elements-commands/backup-element-xmla.md), [Restore](../xml-elements-commands/restore-element-xmla.md), or [Synchronize](../xml-elements-commands/synchronize-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
<Location>  
   ...  
   <DataSourceID>...</DataSourceID>  
   ...  
</Location>  
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
|Parent elements|[Location](../xml-elements-properties/location-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **DataSourceID** element contains the name of the data source on the source instance that identifies the remote instance on which remote partition information is to be backed up, restored, or synchronized.  
