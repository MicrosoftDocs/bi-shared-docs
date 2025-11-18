---
title: "DiscoverResponse Element (XMLA) | Microsoft Docs"
description: Learn how the DiscoverResponse element contains the information returned by an instance of Analysis Services in response to a Discover method call.
ms.date: 01/05/2021
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
---
# XML Elements - Objects - DiscoverResponse

  Contains the information returned by an instance of Analysis Services in response to a [Discover](xml-elements-methods-discover.md) method call.  
  
 **Namespace** urn:schemas-microsoft-com:xml-analysis  
  
## Syntax  
  
```xml  
  
<DiscoverResponse>  
   <return>  
</DiscoverResponse>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[return](xml-elements-properties/return-element-xmla.md)|  
  
## Remarks

 The **DiscoverResponse** element is the topmost element within the body of a SOAP response for the **Discover** method.
