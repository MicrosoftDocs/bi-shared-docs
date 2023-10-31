---
title: "ServerProperty Element (ASSL) | Microsoft Docs"
description: Learn about the ServerProperty object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# ServerProperty Element (ASSL)

  Defines a server property associated with a [Server](../objects/server-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<ServerProperties>  
   <ServerProperty>  
      <Name>...</Name>  
      <Value>...</Value>  
            <RequiresRestart>...</RequiresRestart>  
            <PendingValue>...</PendingValue>  
      <DefaultValue>...</DefaultValue>  
      <DisplayFlag>...</DisplayFlag>  
   </ServerProperty>  
</ServerProperties>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[ServerProperties](../collections/serverproperties-element-assl.md)|  
|Child elements|[DefaultValue](../properties/defaultvalue-element-assl.md), [DisplayFlag](../properties/displayflag-element-assl.md), [Name](../properties/name-element-assl.md), [PendingValue](../properties/pendingvalue-element-assl.md), [RequiresRestart](../properties/requiresrestart-element-assl.md), [Value](../properties/value-element-assl.md)|  
  
## Remarks  
 The **ServerProperty** element describes the data and metadata for a server property associated with an instance of Analysis Services. Unlike elements contained by other collections in the Analysis Services Scripting Language (ASSL), the **ServerProperty** element uses name/value pairs instead of explicitly named elements to describe server properties. The name/value pairs provide for flexibility and extensibility.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ServerProperty>.  
  
## See Also  
 [Server Element &#40;ASSL&#41;](../objects/server-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  
