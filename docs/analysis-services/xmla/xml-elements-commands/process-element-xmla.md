---
title: "Process Element (XMLA) | Microsoft Docs"
description: Learn how the Process element processes objects on a Analysis Services instance.
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
# Process Element (XMLA)

  Processes objects on a Analysis Services instance.  
  
## Syntax  
  
```xml  
  
<Command>  
   <Process>  
      <Type>...</Type>  
      <Object>...</Object>  
      <Bindings>...</Bindings>  
      <DataSource>...</DataSource>  
      <DataSourceView>...</DataSourceView>  
      <ErrorConfiguration>...</ErrorConfiguration>  
      <WriteBackTableCreation>...</WriteBackTableCreation>  
   </Process>  
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
|Child elements|[Bindings](../xml-elements-properties/bindings-element-xmla.md), [DataSource](../xml-elements-properties/datasource-element-xmla.md), [DataSourceView](../xml-elements-properties/datasourceview-element-xmla.md), [ErrorConfiguration](../xml-elements-properties/errorconfiguration-element-xmla.md), [Object](../xml-elements-properties/object-element-xmla.md), [Type Element &#40;XMLA&#41;](../xml-elements-properties/type-element-xmla.md), [WriteBackTableCreation](../xml-elements-properties/writebacktablecreation-element-xmla.md)|  
  
## Remarks  
