---
title: "DataSize Element (ASSL) | Microsoft Docs"
description: Learn about the DataSize property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# DataSize Element (ASSL)

  Contains the size in bytes of a [DataItem](../data-type/dataitem-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<DataItem>  
   ...  
   <DataSize>...</DataSize>  
   ...  
</DataItem  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **DataSize** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DataItem>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
