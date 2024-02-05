---
title: "RootMemberIf Element (ASSL) | Microsoft Docs"
description: Learn about the RootMemberIf property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# RootMemberIf Element (ASSL)

  Determines how the root member or members of a parent attribute are identified.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute>  
   ...  
   <RootMemberIf>...</RootMemberIf>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*ParentIsBlankSelfOrMissing*|  
|Cardinality|0-1: Optional element that can occur once and only once|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of the **RootMemberIf** element is used only by parent attributes (in other words, the value of the [Usage](usage-element-dimensionattribute-assl.md) element of the **DimensionAttribute** parent element is set to *Parent*) to determine the root (topmost) members of a parent-child hierarchy.  
  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*ParentIsBlankSelfOrMissing*|Only members that meet one or more of the conditions described for *ParentIsBlank*, *ParentIsSelf*, or *ParentIsMissing* are treated as root members.|  
|*ParentIsBlank*|Only members with a null, a zero, or an empty string in the key columns represented by the [KeyColumns](../collections/keycolumns-element-assl.md) collection of **DimensionAttribute** are treated as root members.|  
|*ParentIsSelf*|Only members with themselves as parents are treated as root members.|  
|*ParentIsMissing*|Only members with parents that cannot be found are treated as root members.|  
  
 The enumeration that corresponds to the allowed values for **RootMemberIf** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.RootIfValue>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
