---
title: "DbpropMsmdRequestMemoryLimit Element (XMLA) | Microsoft Docs"
Description: Learn how the DbpropMsmdRequestMemoryLimit element overrides the Memory\QueryMemoryLimit server property value for a request. 
ms.date: 08/21/2019
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# DbpropMsmdRequestMemoryLimit Element (XMLA)

  Overrides the Memory\QueryMemoryLimit server property value for a request. 
  
## Syntax  
  
```xml  
  
<PropertyList>  
   ...  
   <DbpropMsmdRequestMemoryLimit>...</DbpropMsmdRequestMemoryLimit>    
   ...  
</PropertyList>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|None|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[PropertyList](../xml-elements-properties/propertylist-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  

The DbpropMsmdRequestMemoryLimit property is specified in kilobytes.