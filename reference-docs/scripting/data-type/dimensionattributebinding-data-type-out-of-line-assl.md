---
title: "DimensionAttributeBinding Data Type (out-of-line) (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# DimensionAttributeBinding Data Type (out-of-line) (ASSL)

  Defines a derived data type that represents an out-of-line binding for an attribute in a dimension.  
  
## Syntax  
  
```xml  
  
<DimensionAttributeBinding>  
   <!-- The following elements extend Binding -->  
   <DatabaseID>...</DatabaseID>  
   <DimensionID>...</DimensionID>  
   <AttributeID>...</AttributeID>  
   <KeyColumns>...</KeyColumns>  
   <NameColumn>...</NameColumn>  
   <Translations>...</Translations>  
</DimensionAttributeBinding>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|[Binding](binding-data-type-assl.md)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[AttributeID](../properties/attributeid-element-assl.md), [DatabaseID](../../../analysis-services/xmla/xml-elements-properties/databaseid-element-xmla.md), [DimensionID](../properties/dimensionid-element-assl.md), [KeyColumns](../collections/keycolumns-element-assl.md), [NameColumn](../objects/namecolumn-element-assl.md), [Translations](../collections/translations-element-assl.md)|  
|Derived elements|[Binding](../../../analysis-services/xmla/xml-elements-properties/binding-element-xmla.md) ([Bindings](../collections/attributes-element-assl.md) collection of XML for Analysis (XMLA) [Batch](../../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md) and [Process](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md) commands)|  
  
## Remarks  
 For more information about out-of-line bindings, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
