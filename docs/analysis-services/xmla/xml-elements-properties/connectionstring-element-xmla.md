---
title: "ConnectionString Element (XMLA) | Microsoft Docs"
description: Learn how the ConnectionString element contains a connection string used by the parent Location or Source element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
ms.custom:
  - xmla
  - sfi-ropc-nochange

---
# ConnectionString Element (XMLA)

  Contains a connection string used by the parent [Location](../xml-elements-properties/location-element-xmla.md) or [Source](../xml-elements-properties/source-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Location> <!-- or Source -->  
   ...  
   <ConnectionString>...</ConnectionString>  
   ...  
</Location>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|See the table below.|  
  
|Ancestor or Parent|Cardinality|  
|------------------------|-----------------|  
|[Location](../xml-elements-properties/location-element-xmla.md)|1-1: Required element that occurs once and only once.|  
|[Source](../xml-elements-properties/source-element-xmla.md)|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Location](../xml-elements-properties/location-element-xmla.md), [Source](../xml-elements-properties/source-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 For **Location** elements, the **ConnectionString** element contains the connection string used by the **Restore** or **Synchronize** command to either update a local data source or connect to a remote instance.  
  
 For **Source** elements, the **ConnectionString** element contains the connection string used by the **Synchronize** command to connect to the source instance.  
