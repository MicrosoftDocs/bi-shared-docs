---
title: "Message Element (XMLA) | Microsoft Docs"
description: Learn how the Message element contains a message returned from an instance of Analysis Services by a Discover or Execute method call.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Message Element (XMLA)

  Contains a message returned from an instance of Analysis Services by a [Discover](../xml-elements-methods-discover.md) or [Execute](../xml-elements-methods-execute.md) method call.  
  
## Syntax  
  
```xml  
  
<Messages>  
   ...  
   <Message>  
      <Error>...</Error>  
      <!-- or -->  
      <Warning>...</Warning>  
   </Message>  
   ...  
</Messages>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Messages](../xml-elements-properties/messages-element-xmla.md)|  
|Child elements|[Error](../xml-elements-properties/error-element-xmla.md), [Warning](../xml-elements-properties/warning-element-xmla.md)|  
  
## Remarks  
 This element is used in cases where a **Discover** method call or a single XMLA command within an **Execute** method call completes successfully, but with errors or warnings. In such cases, a **Messages** element is added to the root element after all other elements, which in turn contains one or more **Message** elements. Each **Message** element represents a single message, either an error or a warning, returned by the Analysis Services instance.  
  