---
title: "return Element (XMLA) | Microsoft Docs"
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
# return Element (XMLA)

  Contains information returned by a [DiscoverResponse](../xml-elements-objects-discoverresponse.md) element in response to a [Discover](../xml-elements-methods-discover.md) method call or an [ExecuteResponse](../xml-elements-objects-executeresponse.md) element in response to an [Execute](../xml-elements-methods-execute.md) method call.  
  
## Syntax  
  
```xml  
  
<DiscoverResponse> <!-- or ExecuteResponse -->  
   <return>  
      <root>...</root>  
      <!-- or -->  
      <results>...</results> <!-- ExecuteResponse only -->  
   </return>  
</DiscoverResponse>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DiscoverResponse](../xml-elements-objects-discoverresponse.md), [ExecuteResponse](../xml-elements-objects-executeresponse.md)|  
|Child elements|See the table below.|  
  
|Ancestor|Child elements|  
|--------------|--------------------|  
|[DiscoverResponse](../xml-elements-objects-discoverresponse.md)|[root](../xml-elements-properties/root-element-xmla.md)|  
|[ExecuteResponse](../xml-elements-objects-executeresponse.md)|[root](../xml-elements-properties/root-element-xmla.md) or [results](../xml-elements-properties/results-element-xmla.md)|  
  
## Remarks  
 The **return** element contains the data returned by the **Discover** and **Execute** methods. Typically, the **return** element contains a single **root** element that contains either the data returned by a successful **Discover** or **Execute** method call or an XML for Analysis (XMLA) exception returned by an unsuccessful method call. If the **Execute** method contains a **Batch** command that performs multiple operations, the **return** element contains a **results** element which, in turn, contains one **root** element for each command executed successfully or unsuccessfully by the **Batch** command.  
