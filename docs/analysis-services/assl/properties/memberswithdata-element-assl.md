---
title: "MembersWithData Element (ASSL) | Microsoft Docs"
description: Learn about the MembersWithData property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# MembersWithData Element (ASSL)

  Determines whether to display data members for non-leaf members in the parent attribute.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute>  
   ...  
   <MembersWithData>...</MembersWithData>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*NonLeafDataVisible*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of the **MembersWithData** element is used only by parent attributes (in other words, the value of the [Usage](usage-element-dimensionattribute-assl.md) element of the **DimensionAttribute** parent element is set to *Parent*) to determine whether to display data members for non-leaf members in the parent attribute. 
  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*NonLeafDataHidden*|Non-leaf data is hidden.|  
|*NonLeafDataVisible*|Non-leaf data is visible.|  
  
 The enumeration that corresponds to the allowed values for **MembersWithData** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MembersWithData>.  
  
