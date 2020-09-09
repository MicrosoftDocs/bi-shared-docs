---
title: "Headers (XMLA) | Microsoft Docs"
description: Learn how the XMLA protocol uses XML elements within the SOAP header to manage protocol-level features, such as session support and the negotiation of supported features.
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
# XML Elements - Headers

  The XML for Analysis (XMLA) protocol uses XML elements within the SOAP header to manage protocol-level features, such as session support and the negotiation of supported features.  
  
## In this section  
 The following topics describe the XMLA header elements implemented by Analysis Services.  
  
|Method|Description|  
|------------|-----------------|  
|[BeginSession Element &#40;XMLA&#41;](../xml-elements-headers/beginsession-element-xmla.md)|Uses a SOAP header in a SOAP request message to start a new session on an instance.|  
|[EndSession Element &#40;XMLA&#41;](../xml-elements-headers/endsession-element-xmla.md)|Uses the SOAP header in a SOAP request message to end an existing session on an instance.|  
|[Session Element &#40;XMLA&#41;](../xml-elements-headers/session-element-xmla.md)|Uses the SOAP header in a SOAP request message to identify an existing, explicit session on an instance.|  
|[ProtocolCapabilities Element &#40;XMLA&#41;](../xml-elements-headers/protocolcapabilities-element-xmla.md)|Uses the SOAP header in a SOAP request message to identify protocol capabilities between an instance and a client application.| 