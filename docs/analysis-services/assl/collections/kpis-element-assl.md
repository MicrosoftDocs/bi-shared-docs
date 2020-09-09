---
title: "Kpis Element (ASSL) | Microsoft Docs"
description: Learn about the Kpis collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Kpis Element (ASSL)

  Contains the collection of key performance indicators ([Kpi](../objects/kpi-element-assl.md) elements) associated with the parent element.  
  
## Syntax  
  
```xml  
  
<Cube><!-- or Perspective -->  
   ...  
   <Kpis>  
      <Kpi>...</Kpi> <!-- parent: Cube -->  
<!-- or -->  
      <Kpi xsi:type="PerspectiveKpi">...</Kpi> <!-- parent: Perspective -->  
   ...  
</Cube>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cube](../objects/cube-element-assl.md), [Perspective](../objects/perspective-element-assl.md)|  
|Child elements|See the table below.|  
  
|Ancestor or Parent|Child Element|  
|------------------------|-------------------|  
|[Cube](../objects/cube-element-assl.md)|[Kpi](../objects/kpi-element-assl.md)|  
|[Perspective](../objects/perspective-element-assl.md)|[Kpi](../objects/kpi-element-assl.md) of type [PerspectiveKpi](../data-type/perspectivekpi-data-type-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.KpiCollection>.  
