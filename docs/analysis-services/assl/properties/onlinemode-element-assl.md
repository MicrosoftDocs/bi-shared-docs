---
title: "OnlineMode Element (ASSL) | Microsoft Docs"
description: Learn about the OnlineMode property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# OnlineMode Element (ASSL)

  Specifies whether the database is brought back online immediately when the rebuilding of the cache is initiated, or only when the rebuilding of the cache is complete.  
  
## Syntax  
  
```xml  
  
<ProactiveCaching>  
   ...  
   <OnlineMode>...</OnlineMode>  
   ...  
</ProactiveCaching>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Immediate*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ProactiveCaching](../objects/proactivecaching-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Immediate*|Database is brought back online immediately when the rebuilding of the cache is initiated.|  
|*OnCacheComplete*|Database is brought back online only when the rebuilding of the cache is complete.|  
  
 The enumeration that corresponds to the allowed values for **OnlineMode** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ProactiveCaching>.  
  
## See Also  
 [ProactiveCaching Element &#40;ASSL&#41;](../objects/proactivecaching-element-assl.md)  
  
  
