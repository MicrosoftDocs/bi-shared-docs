---
title: "root Element (XMLA) | Microsoft Docs"
description: Learn how the root element contains a result returned by the Discover method or an XML for Analysis (XMLA) command executed using the Execute method.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# root Element (XMLA)

  Contains a result returned by the [Discover](../xml-elements-methods-discover.md) method or an XML for Analysis (XMLA) command executed using the [Execute](../xml-elements-methods-execute.md) method.  
  
## Syntax  
  
```xml  
  
<return> <!-- or results-->  
   ...  
   <root xmlns="urn:schemas-microsoft-com:xml-analysis:mddataset">...</root> <!-- for Execute method only -->  
   <!-- or -->  
   <root xmlns="urn:schemas-microsoft-com:xml-analysis:rowset">...</root>  
   <!-- or -->  
   <root xmlns= xmlns="urn:schemas-microsoft-com:xml-analysis:empty">...</root>  
   ...  
</return>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|See the table below.|  
|Default value|None|  
|Cardinality|1-n: Required element that can occur more than once.|  
  
|Ancestor|Data type|  
|--------------|---------------|  
|[DiscoverResponse](../xml-elements-objects-discoverresponse.md)|[Rowset](../xml-data-types/rowset-data-type-xmla.md), [olapxmla_EmptyResult](../xml-data-types/emptyresult-data-type-xmla.md)|  
|[ExecuteResponse](../xml-elements-objects-executeresponse.md)|[MDDataSet](../xml-data-types/mddataset-data-type-xmla.md), [Rowset](../xml-data-types/rowset-data-type-xmla.md), [olapxmla_EmptyResult](../xml-data-types/emptyresult-data-type-xmla.md)|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[results](../xml-elements-properties/results-element-xmla.md), [return](../xml-elements-properties/return-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **root** element contains the information returned in either the [DiscoverResponse](../xml-elements-objects-discoverresponse.md) element returned by a single **Discover** method call, or in the [ExecuteResponse](../xml-elements-objects-executeresponse.md) element returned by a single XMLA command executed by a single **Execute** method call.  
