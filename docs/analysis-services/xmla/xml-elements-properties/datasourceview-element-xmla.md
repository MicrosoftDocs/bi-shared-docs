---
title: "DataSourceView Element (XMLA) | Microsoft Docs"
description: Learn how the DataSourceView element contains an out-of-line data source view binding for the parent Batch or Process element.
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# DataSourceView Element (XMLA)

  Contains an out-of-line data source view binding for the parent [Batch](../xml-elements-commands/batch-element-xmla.md) or [Process](../xml-elements-commands/process-element-xmla.md) element.  
  
## Syntax  
  
```xml  
  
<Batch> <!-- or Process>  
...  
   <DataSourceView>  
      <DatabaseID>...</DatabaseID>  
      <DataSourceViewID>...</DataSourceViewID>  
   </DataSourceView>  
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
|Child elements|[DatabaseID](../xml-elements-properties/databaseid-element-xmla.md), [DataSourceViewID](../../assl/properties/datasourceviewid-element-assl.md)|  
  
## Remarks  
 The **DataSourceView** element represents an out-of-line binding to a data source view, used by the **Batch** or **Process** command to temporarily override the data source view binding for Analysis Services objects processed by the command.
  
  
