---
title: "Exception Element (XMLA) | Microsoft Docs"
description: Learn how the Exception element indicates that an exception was returned from a Discover or Execute method call.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Exception Element (XMLA)

  Indicates that an exception was returned from a [Discover](../xml-elements-methods-discover.md) or [Execute](../xml-elements-methods-execute.md) method call.  
  
 **Namespace** `http://schemas.microsoft.com/analysisservices/2003/exception`  
  
## Syntax  
  
```xml  
  
<root>  
   ...  
   <Exception />  
   ...  
</root>  
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
|Parent elements|[root](../xml-elements-properties/root-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 If an error occurs during the execution of a **Discover** method call or a single XMLA command in an **Execute** method call that prevents the method or command from completing, the **root** element for that method or command contains an **Exception** element and a **Messages** element. The **Exception** element indicates that an error which prevented the method or command from successfully executing occurred, and the **Messages** element contains the list of error or warning messages related to the error.  