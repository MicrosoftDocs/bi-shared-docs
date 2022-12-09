---
title: "Alias Element (ASSL) | Microsoft Docs"
description: Learn about the Alias property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Alias Element (ASSL)

  Defines an alias for an [Account](../objects/account-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Aliases>  
      <Alias>...</Alias>  
</Aliases>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Aliases](../collections/aliases-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of the **Alias** element is used as an alternate name for the account defined by the **Account** parent element, and helps to identify the combination of account type and aggregation function in a user interface.  
  
 The element that corresponds to the parent of the **Aliases** collection in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Account>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
