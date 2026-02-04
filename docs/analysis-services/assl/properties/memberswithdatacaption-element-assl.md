---
title: "MembersWithDataCaption Element (ASSL) | Microsoft Docs"
description: Learn about the MembersWithDataCaption property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

---
# MembersWithDataCaption Element (ASSL)

  Provides a template string that is used to create captions for system-generated data members.  
  
## Syntax  
  
```xml  
  
<AttributeTranslation> <!-- or DimensionAttribute -->  
   ...  
   <MembersWithDataCaption>...</MembersWithDataCaption>  
   ...  
</AttributeTranslation>  
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
|Parent elements|[AttributeTranslation](../data-type/attributetranslation-data-type-assl.md), [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of the **MembersWithDataCaption** element is used only by parent attributes (in other words, the value of the [Usage](usage-element-dimensionattribute-assl.md) element of the **DimensionAttribute** parent element is set to *Parent*) to determine the caption of data members in the parent attribute.
  
 The elements that correspond to the parents of **MembersWithDataCaption** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.AttributeTranslation> and <xref:Microsoft.AnalysisServices.DimensionAttribute>.  

