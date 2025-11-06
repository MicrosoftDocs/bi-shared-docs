---
title: "Methods (XMLA) | Microsoft Docs"
description: Learn about how the the Discover and Execute XMLA methods allow applications to access information on an instance of Analysis Services. 
ms.date: 01/05/2021
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
---
# XML Elements - Methods

  The XML for Analysis (XMLA) protocol uses two methods, **Discover** and **Execute**, to offer a standard way for applications to access information on an instance of Analysis Services. Because these methods are invoked by using Simple Object Access Protocol (SOAP), they accept input and deliver output in XML. Analysis Services implements both methods, in compliance with the XML for Analysis 1.1 specification.  
  
## In this section

 The following topics describe the XMLA methods implemented by Analysis Services.  
  
|Method|Description|  
|------------|-----------------|  
|[Discover Method &#40;XMLA&#41;](xml-elements-methods-discover.md)|Retrieves information, such as the list of available databases or details about a specific object, from an instance of Analysis Services. The data retrieved with the **Discover** method depends on the values of the parameters passed to it.|  
|[Execute Method &#40;XMLA&#41;](xml-elements-methods-execute.md)|Sends XMLA commands to an instance of Analysis Services. This includes requests involving data transfer, such as retrieving or updating data on the server.|