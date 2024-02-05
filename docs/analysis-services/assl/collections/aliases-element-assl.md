---
title: "Aliases Element (ASSL) | Microsoft Docs"
description: Learn about the Aliases collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Aliases Element (ASSL)

  Contains the collection of [Alias](../properties/alias-element-assl.md) elements associated with an [Account](../objects/account-element-assl.md) element  
  
## Syntax  
  
```xml  
  
<Account>  
      ...  
   <Aliases>  
      <Alias>...</Alias>  
      </Aliases>  
      ...  
</Account>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None (collection)|  
|Default value|None (collection)|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Account](../objects/account-element-assl.md)|  
|Child elements|[Alias](../properties/alias-element-assl.md)|  
  
## Remarks  
 The element corresponding to the parent of **Aliases** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Account>.  

  
  
