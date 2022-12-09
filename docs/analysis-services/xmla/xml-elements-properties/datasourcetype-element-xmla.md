---
title: "DataSourceType Element (XMLA) | Microsoft Docs"
description: Learn how the DataSourceType element indicates whether a Location element specified for a Restore or Synchronize command is local or remote.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# DataSourceType Element (XMLA)

  Indicates whether a [Location](../xml-elements-properties/location-element-xmla.md) element specified for a [Restore](../xml-elements-commands/restore-element-xmla.md) or [Synchronize](../xml-elements-commands/synchronize-element-xmla.md) command is local or remote.  
  
## Syntax  
  
```xml  
  
<Location>  
   ...  
   <DataSourceType>...</DataSourceType>  
   ...  
</Location>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Remote*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Location](../xml-elements-properties/location-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **DataSourceType** element determines whether the data source defined by the **Location** element contains a local data source or a remote data source.
  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Local*|The **Location** element defines a local data source. If this value is used, the **Restore** and **Synchronize** commands use the information defined in the **Location** element to update the data source, retrieved from either the backup file specified in the **File** element for the **Backup** command or the database specified in the **Source** element for the **Synchronize** command, identified in the **DataSourceID** element of the **Location** element.<br /><br /> This value allows objects that use relational OLAP (ROLAP) storage, after being restored or synchronized, to use a different database for their data and metadata.<br /><br /> Note: ROLAP data, such as data in dimension tables or writeback tables, is not restored or synchronized. Only metadata for ROLAP objects is restored or synchronized.|  
|*Remote*|The **Location** element defines a remote data source. If this value is used, the **Restore** and **Synchronize** commands use the information defined in the **Location** element to restore or synchronize remote partitions, retrieved from either the backup file specified in the **File** element of the **Backup** command or the database specified in the **Source** element for the **Synchronize** command, to the remote instance identified in the **DataSourceID** of the **Location** element.|  
