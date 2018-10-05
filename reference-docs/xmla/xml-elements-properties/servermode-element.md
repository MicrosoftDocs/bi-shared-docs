---
title: "ServerMode Element | Microsoft Docs"
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
# ServerMode Element

  The **ServerMode** server element specifies the mode the server is operating in.  
  
## Syntax  
  
```xml  
  
<Server>  
...  
   <ddl300:ServerMode>...</ddl300:ServerMode>  
...  
</Server>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|(none)|  
|Cardinality|0-1: Optional element that can occur only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Server](../../assl/objects/server-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The server operates in either one of the following modes:  
  
|Value|Description|  
|-----------|-----------------|  
|*Multidimensional*|Multidimensional and Data Mining Mode|  
|*Tabular*|Tabular mode|  
|*SharePoint*|SharePoint mode|  
