---
title: "Locations Element (XMLA) | Microsoft Docs"
description: Learn how the Locations element contains a collection of Location elements used by the parent Backup, Restore, or Synchronize command. 
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference

---
# Locations Element (XMLA)

  Contains a collection of [Location](../xml-elements-properties/query-element-xmla.md) elements used by the parent [Backup](../xml-elements-commands/backup-element-xmla.md), [Restore](../xml-elements-commands/restore-element-xmla.md) , or [Synchronize](../xml-elements-commands/synchronize-element-xmla.md) command.  
  
## Syntax  
  
```xml  
  
< Backup> <!-- or one of the elements listed below in the Element relationships table -->  
   ...  
   <Locations>  
      <Location>...</Location>  
   </Locations>  
   ...  
</Backup>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Backup](../xml-elements-commands/backup-element-xmla.md), [Restore](../xml-elements-commands/restore-element-xmla.md) , or [Synchronize](../xml-elements-commands/synchronize-element-xmla.md)|  
|Child elements|[Location](../xml-elements-properties/location-element-xmla.md)|  
  
## Remarks  

