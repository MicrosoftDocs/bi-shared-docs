---
title: "Persistence Element (ASSL) | Microsoft Docs"
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
# Persistence Element (ASSL)

  Determines which parts of the bound source data are dynamic and are checked for updates using the frequency specified by the [RefreshPolicy](refreshpolicy-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<DimensionBinding> <!-- or MeasureGroupBinding -->  
   ...  
   <Persistence>...</Persistence>  
   ...  
</DimensionBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*NotPersisted*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DimensionBinding](../data-type/dimensionbinding-data-type-assl.md), [MeasureGroupBinding](../data-type/measuregroupbinding-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*NotPersisted*|Source metadata, members, and data are all dynamic.|  
|*MetaData*|Source metadata is static, but members and data are dynamic.|  
|*All*|Source metadata, members, and data are all static.|  
  
 The enumeration that corresponds to the allowed values for **Persistence** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.PersistenceType>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
