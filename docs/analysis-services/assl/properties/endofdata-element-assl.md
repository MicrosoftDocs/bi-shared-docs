---
title: "EndOfData Element (ASSL) | Microsoft Docs"
description: Learn about the EndOfData property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# EndOfData Element (ASSL)

  Indicates the end of data received from a [PushedDataSource](../data-type/pusheddatasource-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<PushedDataSource>  
   ...  
   <EndOfData>...</EndOfData>  
   ...  
</PushedDataSource  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|None|  
|Cardinality|1-1: Required element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[PushedDataSource](../data-type/pusheddatasource-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The last data packet from the **PushedDataSource** must set the **EndOfData** element to **True**.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
