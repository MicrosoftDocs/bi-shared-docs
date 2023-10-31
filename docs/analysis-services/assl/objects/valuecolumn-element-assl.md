---
title: "ValueColumn Element (ASSL) | Microsoft Docs"
description: Learn about the ValueColumn object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# ValueColumn Element (ASSL)

  Identifies the column that provides the value of the parent element.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute>  
   ...  
   <ValueColumn xsi:type="DataItem">...</ValueColumn>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Default value|Varies (see Remarks)|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 If the [NameColumn](../objects/namecolumn-element-assl.md) element of **DimensionAttribute** is specified, the same **DataItem** values are used as default values for the **ValueColumn** element. If the **NameColumn** element of **DimensionAttribute** is not specified and the [KeyColumns](../collections/keycolumns-element-assl.md) collection of **DimensionAttribute** contains a single [KeyColumn](../objects/keycolumn-element-assl.md) element representing a key column with a string data type, the same **DataItem** values are used as default values for the **ValueColumn** element.  
  
 For more information about the **DataItem** type, including a table of Analysis Services Scripting Language (ASSL) objects and properties of the **DataItem** type, see [DataItem Data Type &#40;ASSL&#41;](../data-type/dataitem-data-type-assl.md).  
  
 The elements that correspond to the parents of **NameColumn** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.DimensionAttribute> and <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  
