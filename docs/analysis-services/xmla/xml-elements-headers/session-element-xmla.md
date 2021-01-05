---
title: "Session Element (XMLA) | Microsoft Docs"
description: Learn how the Session element uses the SOAP header in a SOAP request message to identify an existing, explicit session on an instance of Analysis Services.
ms.date: 01/05/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Session Element (XMLA)

  Uses the SOAP header in a SOAP request message to identify an existing, explicit session on an instance of Analysis Services.  
  
 **Namespace** urn:schemas-microsoft-com:xml-analysis  
  
## Syntax  
  
```xml  
  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
   <soap:Header>  
      ...  
      <Session  
         xmlns="urn:schemas-microsoft-com:xml-analysis"  
         SessionId="string" />  
      ...  
   </soap:Header>  
   <soap:Body>  
      ...  
   </soap:Body>  
</soap:Envelope>  
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
|Parent elements|None|  
|Child elements|None|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|SessionId|Required **String** attribute that identifies the session to be used. The server instance uses a globally unique identifier (GUID) to identify a session.|  
  
## Remarks  
 The **Session** header element identifies an existing, explicitly started session on the instance. The **Session** element is part of the SOAP header in the following types of messages:  
  
-   A SOAP response that contains a [BeginSession](../xml-elements-headers/beginsession-element-xmla.md) SOAP header element.  
  
-   A SOAP request to identify the session on which to run the [Discover](../xml-elements-methods-discover.md) or [Execute](../xml-elements-methods-execute.md) method.  
  
 A session identifier does not guarantee that a session remains valid. The session specified in the **Session** element can expire. For example, a session can expire if the session times out or the connection associated with the session is disconnected. If the session expires and is no longer valid, the server ends the session and rolls back any transaction currently in process. Any SOAP message sent with a session identifier that is no longer valid fails with a SOAP fault indicating that the specified session cannot be found.  
  
 If a **Session** element is not sent as part of a SOAP request, the instance implicitly begins a session for the duration of the **Discover** or **Execute** method call, and then ends that session once the method call has completed.