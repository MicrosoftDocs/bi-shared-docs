---
title: "LastSchemaUpdate Element (XMLA) | Microsoft Docs"
description: Learn how the LastSchemaUpdate element contains the date and time that the metadata of the cube represented by the parent Cube element was last updated.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# LastSchemaUpdate Element (XMLA)

  Contains the date and time that the metadata of the cube represented by the parent [Cube](../xml-elements-properties/cube-element-olapinfo-xmla.md) element was last updated.  
  
## Syntax  
  
```xml  
  
<Cube>  
   ...  
   <LastSchemaUpdate>...</LastSchemaUpdate>  
   ...  
</Cube>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|dateTime|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cube](../xml-elements-properties/cube-element-olapinfo-xmla.md)|  
|Child elements|None|  
  
## Remarks  
