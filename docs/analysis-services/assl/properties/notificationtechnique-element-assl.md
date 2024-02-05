---
title: "NotificationTechnique Element (ASSL) | Microsoft Docs"
description: Learn about the NotificationTechnique property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# NotificationTechnique Element (ASSL)

  Specifies whether  or an external client application processes the notifications.  
  
## Syntax  
  
```xml  
  
<ProactiveCachingBinding>  
   <NotificationTechnique>...</NotificationTechnique>  
</ProactiveCachingBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Client*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[ProactiveCachingBinding](../data-type/proactivecachingbinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Client*|External client application processes the notification.|  
|*Server*|Processes the notification.|  
  
 The element that corresponds to the parent of **NotificationTechnique** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ProactiveCachingBinding>.  
  
 The enumeration that corresponds to the allowed values for **NotificationTechnique** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.NotificationTechnique>.  
  
## See Also  
 [ProactiveCachingBinding Data Type &#40;ASSL&#41;](../data-type/proactivecachingbinding-data-type-assl.md)  
  
  
