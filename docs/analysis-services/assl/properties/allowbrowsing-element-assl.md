---
title: "AllowBrowsing Element (ASSL) | Microsoft Docs"
description: Learn about the AllowBrowsing property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# AllowBrowsing Element (ASSL)

  Defines whether the members of a [Role](../objects/role-element-assl.md) element have browse permission on a [MiningModel](../objects/miningmodel-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MiningModelPermission>  
      ...  
   <AllowBrowsing>...</AllowBrowsing>  
   ...  
</MiningModelPermission>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|**True**|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[MiningModelPermission](../objects/miningmodelpermission-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **AllowBrowsing** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningModelPermission>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
