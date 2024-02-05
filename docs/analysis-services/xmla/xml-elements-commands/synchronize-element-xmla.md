---
title: "Synchronize Element (XMLA) | Microsoft Docs"
description: Learn how the Synchronize element synchronizes a Analysis Services database with another existing database.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Synchronize Element (XMLA)

  Synchronizes a Analysis Services database with another existing database.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Synchronize>  
      <Source>...</Source>  
      <SynchronizeSecurity>...</SynchronizeSecurity>  
      <ApplyCompression>...</ApplyCompression>  
      <Locations>...</Locations>  
   </Synchronize>  
</Command>  
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
|Parent elements|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Child elements|[ApplyCompression](../xml-elements-properties/applycompression-element-xmla.md), [Locations](../xml-elements-properties/locations-element-xmla.md), [Source](../xml-elements-properties/source-element-synchronize-xmla.md), [SynchronizeSecurity](../xml-elements-properties/synchronizesecurity-element-xmla.md)|  
  
## Remarks  
 The **Synchronize** command synchronizes the target database with a source instance and database specified in the **Source** element. Optionally, the **Synchronize** command synchronizes remote partitions defined on the source database.  
  
 Depending on the storage mode used by objects stored in the backup file, the **Synchronize** command synchronizes information as listed in the following table.  
  
|Storage mode|Information|  
|------------------|-----------------|  
|Multidimensional OLAP (MOLAP)|Source data, aggregations, and metadata|  
|Hybrid OLAP (HOLAP)|Aggregations and metadata|  
|Relational OLAP (ROLAP)|Metadata|  
  
 During a **Synchronize** command, a read lock is placed on the source database and a write lock is placed on the target database. Both locks are released after the **Synchronize** command has completed.  
