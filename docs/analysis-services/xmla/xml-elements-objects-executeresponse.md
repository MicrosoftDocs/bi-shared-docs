---
title: "ExecuteResponse Element (XMLA) | Microsoft Docs"
description: Learn how the ExecuteResponse element contains the information returned by an instance of Analysis Services in response to an Execute method call.
ms.date: 01/05/2021
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# XML Elements - Objects - ExecuteResponse

  Contains the information returned by an instance of Analysis Services in response to an [Execute](xml-elements-methods-execute.md) method call.  
  
 **Namespace** urn:schemas-microsoft-com:xml-analysis  
  
## Syntax  
  
```xml  
  
<ExecuteResponse>  
   <return>  
</ExecuteResponse>  
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

 The **ExecuteResponse** element is the topmost element within the body of a SOAP response for the **Execute** method.