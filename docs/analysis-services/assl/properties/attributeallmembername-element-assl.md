---
title: "AttributeAllMemberName Element (ASSL) | Microsoft Docs"
description: Learn about the AttributeAllMemberName property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# AttributeAllMemberName Element (ASSL)

  Contains the caption, in the default language, for the All member of the dimension.  
  
## Syntax  
  
```xml  
  
<Dimension>  
      ...  
   <AttributeAllMemberName>...</AttributeAllMemberName>  
   ...  
</Dimension>  
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
|Parent element|[Dimension](../objects/dimension-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The element that corresponds to the parent of **AttributeAllMemberName** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Dimension>.  

  
  
