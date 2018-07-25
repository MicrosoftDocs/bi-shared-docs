---
title: "Version Element (ASSL) | Microsoft Docs"
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
# Version Element (ASSL)

  Contains the read-only version number of the instance of Analysis Services represented by the [Server](../objects/server-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Server>  
      ...  
      <Version>...</Version>  
   ...  
</Server>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Server](../objects/server-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **Version** element describes which version ofAnalysis Services is installed.  
  
 The element that corresponds to the parent of **Version** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Server>.  
  
## See Also  
 [Edition Element &#40;ASSL&#41;](edition-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
