---
title: "KpiID Element (ASSL) | Microsoft Docs"
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# KpiID Element (ASSL)

  Contains an identifier (ID) that associates a [Kpi](../objects/kpi-element-assl.md) element with a [Perspective](../objects/perspective-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<PerspectiveKpi>  
      ...  
   <KpiID>...</KpiID>  
   ...  
</PerspectiveKpi>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[PerspectiveKpi](../data-type/perspectivekpi-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **KpiID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.PerspectiveKpi>.  
  
## See Also  
 [Properties (ASSL)](properties-assl.md)  
  
  
