---
title: "DataSource Element (XMLA) | Microsoft Docs"
description: Learn how the DataSource element contains an out-of-line data source binding for the parent Batch or Process element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# DataSource Element (XMLA)

  Contains an out-of-line data source binding for the parent [Batch](../xml-elements-commands/batch-element-xmla.md) or [Process](../xml-elements-commands/process-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Batch> <!-- or Process>  
...  
   <DataSource>  
      <DatabaseID>...</DatabaseID>  
      <DataSourceID>...</DataSourceID>  
   </DataSource>  
...  
</Batch>  
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
|Parent elements|[Batch](../xml-elements-commands/batch-element-xmla.md), [Process](../xml-elements-commands/process-element-xmla.md)|  
|Child elements|[DatabaseID](../xml-elements-properties/databaseid-element-xmla.md), [DataSourceID](../xml-elements-properties/datasourceid-element-xmla.md)|  
  
## Remarks  
 The **DataSource** element represents an out-of-line binding to a data source, used by the **Batch** or **Process** command to temporarily override the data source binding for Analysis Services objects processed by the command.  
