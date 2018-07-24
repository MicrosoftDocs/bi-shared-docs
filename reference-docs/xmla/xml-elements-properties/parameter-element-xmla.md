---
title: "Parameter Element (XMLA) | Microsoft Docs"
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
# Parameter Element (XMLA)

  Contains the name and value of a parameter used by the [Execute](../xml-elements-methods-execute.md) method.  
  
## Syntax  
  
```  
  
<Parameters>  
...  
   <Parameter>  
      <Name>...</Name>  
      <Value>...</Value>  
   </Parameter>  
...  
</Parameters>  
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
|Parent elements|[Parameters](../xml-elements-properties/parameters-element-xmla.md)|  
|Child elements|[Name](../xml-elements-properties/name-element-parameter-xmla.md), [Value](../xml-elements-properties/value-element-parameter-xmla.md)|  
  
## Remarks  
 Some XML for Analysis (XMLA) commands, such as the [Process](../xml-elements-commands/process-element-xmla.md) command, can require additional information. The **Parameter** element provides a mechanism for providing additional information, including chunked information, for an XMLA command.  
