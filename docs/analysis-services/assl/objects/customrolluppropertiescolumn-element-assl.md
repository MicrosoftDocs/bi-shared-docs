---
title: "CustomRollupPropertiesColumn Element (ASSL) | Microsoft Docs"
description: Learn about the CustomRollupPropertiesColumn object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# CustomRollupPropertiesColumn Element (ASSL)

  Defines the details of a column that provide the properties of a custom rollup formula.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute>  
   ...  
   <CustomRollupPropertiesColumn xsi:type="DataItem">...</CustomRollupPropertiesColumn>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 For additional information about the **DataItem** type, including a table of Analysis Services Scripting Language (ASSL) objects and properties of the **DataItem** type, see [DataItem Data Type &#40;ASSL&#41;](../data-type/dataitem-data-type-assl.md).  
  
 The element that corresponds to the parent of **CustomRollupPropertiesColumn** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DimensionAttribute>.  
  
## See Also  
 [CustomRollupColumn Element &#40;ASSL&#41;](../objects/customrollupcolumn-element-assl.md)   
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  
