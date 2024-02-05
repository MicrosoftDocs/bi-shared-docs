---
title: "ProtocolCapabilities Element (XMLA) | Microsoft Docs"
description: Learn how the ProtocolCapabilities element uses the SOAP header in a SOAP request message to identify protocol capabilities between an instance of Analysis Services and a client application. 
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# ProtocolCapabilities Element (XMLA)

  Uses the SOAP header in a SOAP request message to identify protocol capabilities between an instance of Analysis Services and a client application.  
  
 **Namespace** `http://schemas.microsoft.com/analysisservices/2003/engine`  
  
## Syntax  
  
```xml  
  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
   <soap:Header>  
      ...  
      <ProtocolCapabilities xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
         <Capability>...</Capability>  
      </ProtocolCapabilities>  
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
|Child elements|[Capability](../xml-elements-properties/capability-element-xmla.md)|  
  
## Remarks  
 The **ProtocolCapabilities** element enables client applications to negotiate protocol capabilities, such as binary XML or compression support, with a server instance at any time. Protocol negotiation involves the following steps:  
  
1.  The client application identifies its protocol capability by sending a SOAP request that includes the **ProtocolCapabilities** element as part of the SOAP header.  
  
2.  The instance receives and processes the SOAP request.  
  
3.  If the instance has the same protocol capability as that requested, the instance sends a SOAP response that includes the same **ProtocolCapabilities** element sent in the SOAP request, and the protocol has been successfully negotiated. Otherwise, the protocol capabilities are not successfully negotiated, and the instance returns a SOAP fault.  
  
 After successfully negotiating protocol capabilities, how long the client application and the instance use a particular protocol depends upon whether the session is explicit or implicit:  
  
-   An explicit session is one that is created using the [BeginSession](../xml-elements-headers/beginsession-element-xmla.md) header element. For an explicit session, the negotiated protocol is used until either the client application sends a new **ProtocolCapabilities** element or the session ends.  
  
-   An implicit session is one that is created by an instance and not explicitly specified by the client application when submitting a SOAP request. For an implicit session, the negotiated protocol is used only until the SOAP request is completed.  
  
 Protocol capabilities do not have to be explicitly negotiated. That is, a client application does not have to include a **ProtocolCapabilities** element as part of the SOAP request. If a SOAP request does not include a **ProtocolCapabilities** element, the instance responds using the same format as the SOAP request. 