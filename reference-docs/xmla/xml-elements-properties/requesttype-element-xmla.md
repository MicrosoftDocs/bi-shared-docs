---
title: "RequestType Element (XMLA) | Microsoft Docs"
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
# RequestType Element (XMLA)

  Determines the type of metadata returned by the [Discover](../xml-elements-methods-discover.md) method.  
  
## Syntax  
  
```xml  
  
<Discover>  
   ...  
   <RequestType>...</RequestType>  
   ...  
</Discover>  
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
|Parent elements|[Discover](../xml-elements-methods-discover.md)|  
|Child elements|None|  
  
## Remarks  
 The **RequestType** element determines the schema rowset from which the **Discover** method returns data. This enumeration is limited to the names of the schema rowsets supported by Analysis Services.
  
> [!NOTE]  
>  The **RequestType** element enumerates only schema rowset names. An error occurs if the schema rowset GUID is used.  
