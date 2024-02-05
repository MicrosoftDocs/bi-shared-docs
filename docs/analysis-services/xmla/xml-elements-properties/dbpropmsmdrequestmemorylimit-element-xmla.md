---
title: "DbpropMsmdRequestMemoryLimit Element (XMLA) | Microsoft Docs"
description: Learn how the DbpropMsmdRequestMemoryLimit element overrides the Memory QueryMemoryLimit server property value for a request. 
ms.date: 08/21/2019
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
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