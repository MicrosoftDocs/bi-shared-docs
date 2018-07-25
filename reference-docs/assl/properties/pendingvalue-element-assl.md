---
title: "PendingValue Element (ASSL) | Microsoft Docs"
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# PendingValue Element (ASSL)

  Contains the read-only pending value of the associated [ServerProperty](objects/serverproperty-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<ServerProperty>  
   ...  
   <PendingValue>...</PendingValue>  
   ...  
</ServerProperty>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Any simpleType|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ServerProperty](objects/serverproperty-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 This element contains the value of the **ServerProperty** that will be used the next time the current instance of Analysis Services is started. This value is typically retrieved from wherever the value for the server property is stored—in an initialization file, the  Windows registry, or another storage mechanism.  
  
 The element that corresponds to the parent of **PendingValue** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ServerProperty>.  
  
## See Also  
 [ServerProperties Element &#40;ASSL&#41;](collections/serverproperties-element-assl.md)   
 [Server Element &#40;ASSL&#41;](objects/server-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties/properties-assl.md)  
  
  
