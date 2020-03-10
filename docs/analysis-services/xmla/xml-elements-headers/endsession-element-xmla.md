---
title: "EndSession Element (XMLA) | Microsoft Docs"
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
# EndSession Element (XMLA)

  Uses the SOAP header in a SOAP request message to end an existing session on an instance of Analysis Services.  
  
 **Namespace** urn:schemas-microsoft-com:xml-analysis  
  
## Syntax  
  
```xml  
  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
   <soap:Header>  
      ...  
      <EndSession  
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
|SessionId|Required **String** attribute that identifies the session to be ended. The server uses a globally unique identifier (GUID) to identify a session.|  
  
## Remarks  
 The **EndSession** header element is part of the SOAP request sent to an existing, explicitly started session on an Analysis Services instance. If the **EndSession** header element is sent, but contains a session identifier that is no longer valid, a SOAP fault is returned that indicates that the session cannot be found.  
