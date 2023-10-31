---
title: "NameColumn Element (ASSL) | Microsoft Docs"
description: Learn about the NameColumn object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# NameColumn Element (ASSL)

  Identifies the column that provides the name of the parent element.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute> <!-- or ScalarMiningStructureColumn -->  
   ...  
   <NameColumn xsi:type="DataItem">...</NameColumn>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Default value|See the table below.|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
|Ancestor or Parent|Default Value|  
|------------------------|-------------------|  
|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|Varies (see Remarks)|  
|[ScalarMiningStructureColumn](../data-type/scalarminingstructurecolumn-data-type-assl.md)|None|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md), [ScalarMiningStructureColumn](../data-type/scalarminingstructurecolumn-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 If the [KeyColumns](../collections/keycolumns-element-assl.md) collection of **DimensionAttribute** contains a single [KeyColumn](../objects/keycolumn-element-assl.md) element representing a key column with a string data type, the same **DataItem** values are used as default values for the **NameColumn** element.  
  
 For more information about the **DataItem** type, including a table of Analysis Services Scripting Language (ASSL) objects and properties of the **DataItem** type, see [DataItem Data Type &#40;ASSL&#41;](../data-type/dataitem-data-type-assl.md).  
  
 The elements that correspond to the parents of **NameColumn** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.DimensionAttribute> and <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  
