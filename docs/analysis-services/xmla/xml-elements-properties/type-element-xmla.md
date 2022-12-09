---
title: "Type Element (XMLA) | Microsoft Docs"
description: Learn how the Type element determines the type of processing to be performed by the Process element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Type Element (XMLA)

  Determines the type of processing to be performed by the [Process](../xml-elements-commands/process-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Process>  
...  
   <Type>...</Type>  
...  
</Process>  
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
|Parent elements|[Process](../xml-elements-commands/process-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
  
 The value of the **Type** element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*ProcessFull*|Drops all data in the affected object, and then processes the affected object.|  
|*ProcessAdd*|Adds new data to the affected object.|  
|*ProcessUpdate*|Refreshes the data in the affected object.|  
|*ProcessIndexes*|Creates or rebuilds indexes and aggregations in the affected object.|  
|*ProcessScriptCache*|If the cube is processed, the server will rebuild the MDX script cache. If not, an error will be raised.<br /><br /> **Note** Applies only to cube.|  
|*ProcessData*|Processes data only in the affected object.|  
|*ProcessDefault*|Detects the state of the affected object and then performs the appropriate processing option on the affected object to fully optimize it and return it to a fully processed state.|  
|*ProcessClear*|Drops the data in the affected object and all related objects.|  
|*ProcessStructure*|Processes the structure only of the affected object.|  
|*ProcessClearStructureOnly*|Clears data only from the affected object.|  
