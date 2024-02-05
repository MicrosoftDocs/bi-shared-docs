---
title: "Capability Element (XMLA) | Microsoft Docs"
description: Learn how the Capability element indicates support for a protocol capability in the parent ProtocolCapabilities header element.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
---
# Capability Element (XMLA)

  Indicates support for a protocol capability in the parent [ProtocolCapabilities](../xml-elements-headers/protocolcapabilities-element-xmla.md) header element.  
  
## Syntax  
  
```xml  
  
<ProtocolCapabilities>  
   ...  
   <Capability>...</Capability>  
   ...  
</ProtocolCapabilities>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[ProtocolCapabilities](../xml-elements-headers/protocolcapabilities-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The **Capability** element indicates that a particular capability, such as binary or compression, is supported by either the application that included the **ProtocolCapabilities** header element in the SOAP header of the SOAP request, or by the instance of Analysis Services that included the **ProtocolCapabilities** header element in the SOAP header of the SOAP response. The value of the **Capability** element is the name of the capability to be supported.  
  
 Analysis Services supports the capabilities listed in the following table.  
  
|Capability name|Description|  
|---------------------|-----------------|  
|sx|Binary XML support|  
|xpress|Compression support|  
  