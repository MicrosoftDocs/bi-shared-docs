---
title: "Messages Element (XMLA) | Microsoft Docs"
description: Learn how the Messages element contains a collection of Message elements returned from an instance of Analysis Services by a Discover or Execute method call.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Messages Element (XMLA)

  Contains a collection of [Message](../xml-elements-properties/message-element-xmla.md) elements returned from an instance of Analysis Services by a [Discover](../xml-elements-methods-discover.md) or [Execute](../xml-elements-methods-execute.md) method call.  
  
## Syntax  
  
```xml  
  
<Resultset>  
   <Messages>  
      <Message>  
   </Messages>  
</Resultset>  
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
|Parent elements|[Resultset](../xml-data-types/resultset-data-type-xmla.md)|  
|Child elements|[Message](../xml-elements-properties/message-element-xmla.md)|  
  
## Remarks  
 This element is used in cases where a **Discover** method call or a single XMLA command within an **Execute** method call completes successfully, but with errors or warnings. In such cases, a **Messages** element is added to the [root](../xml-elements-properties/root-element-xmla.md) element after all other elements, which in turn contains one or more **Message** elements. Each **Message** element represents a single message, either an error or a warning, returned by the Analysis Services instance.  
