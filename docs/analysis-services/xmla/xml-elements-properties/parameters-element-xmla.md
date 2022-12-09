---
title: "Parameters Element (XMLA) | Microsoft Docs"
description: Learn how the Parameters element contains a collection of Parameter elements used by the Execute method.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Parameters Element (XMLA)

  Contains a collection of [Parameter](../xml-elements-properties/parameter-element-xmla.md) elements used by the [Execute](../xml-elements-methods-execute.md) method.  
  
 **Namespace:** `urn:schemas-microsoft-com:xml-analysis`  
  
## Syntax  
  
```xml  
  
<Execute>  
...  
   <Parameters>  
      <Parameter>...</Parameter>  
   </Parameters>  
...  
</Execute>  
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
|Parent elements|[Execute](../xml-elements-methods-execute.md)|  
|Child elements|[Parameter](../xml-elements-properties/parameter-element-xmla.md)|  
  
## Remarks  
 Some XML for Analysis (XMLA) commands, such as the [Process](../xml-elements-commands/process-element-xmla.md) command, can require additional information. The **Parameters** element provides a mechanism for providing additional information, including chunked information, for an XMLA command.  
  
 If the XMLA command does not use the **Parameters** element, the element can be omitted when calling the **Execute** method.  
