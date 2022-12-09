---
title: "Mode Element (XMLA) | Microsoft Docs"
description: Learn how the Mode element identifies the mode to be used by the parent [Lock](../xml-elements-commands/lock-element-xmla.md) element when creating a lock on a specified object.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Mode Element (XMLA)

  Identifies the mode to be used by the parent [Lock](../xml-elements-commands/lock-element-xmla.md) element when creating a lock on a specified object.  
  
## Syntax  
  
```xml  
  
<Lock>  
   ...  
   <Mode>...</Mode>  
   ...  
</Lock>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Lock](../xml-elements-commands/lock-element-xmla.md), [Unlock](../xml-elements-commands/unlock-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The parent **Lock** element uses the **Mode** element to determine the type of lock to create on an object. The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*CommitShared*|A shared lock is established on the specified object. Other shared locks can be created for the same object.<br /><br /> A shared lock prevents transactions containing write operations, such as an [Execute](../xml-elements-methods-execute.md) method call running an [Alter](../xml-elements-commands/alter-element-xmla.md) command, on a specified object, from committing until the shared lock is removed. A shared lock does not prevent transactions containing read operations, such as a [Discover](../xml-elements-methods-discover.md) method call or an **Execute** method call running a [Statement](../xml-elements-commands/statement-element-xmla.md) command, from committing.|  
|*CommitExclusive*|An exclusive lock is established on the specified object. Other shared or exclusive locks cannot be created for the same object.<br /><br /> An exclusive lock prevents transactions containing either read or write operations on a specified object from committing until the exclusive lock is removed.|  
