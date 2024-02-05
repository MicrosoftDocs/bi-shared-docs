---
title: "DataItem Data Type (ASSL) | Microsoft Docs"
description: Learn about the DataItem data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# DataItem Data Type (ASSL)

  Defines a primitive data type that represents the data-related characteristics of a data item, such as a column or attribute.  
  
## Syntax  
  
```xml  
  
<DataItem>  
   <DataType>...</DataType>  
   <DataSize>...</DataSize>  
   <MimeType>...</MimeType>  
   <NullProcessing>...</NullProcessing>  
   <Trimming>...</Trimming>  
   <InvalidXmlCharacters>...</InvalidXmlCharacters>  
      <Collation>...</Collation>  
   <Format>...</Format>  
   <Source>...</Source>  
   <Annotations>...</Annotations>  
</DataItem>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Annotations](../collections/annotations-element-assl.md), [Collation](../properties/collation-element-assl.md), [DataSize](../properties/datasize-element-assl.md), [DataType](../properties/datatype-element-assl.md), [Format](../properties/format-element-assl.md), [InvalidXmlCharacters](../properties/invalidxmlcharacters-element-assl.md), [MimeType](../properties/mimetype-element-assl.md), [NullProcessing](../properties/nullprocessing-element-assl.md), [Source](../properties/source-element-binding-assl.md), [Trimming](../properties/trimming-element-assl.md)|  
|Derived elements|See the table in Remarks.|  
  
## Remarks  
 The **DataItem** data type is used for any data item that can be bound; for example, a measure, attribute key, and attribute name. The details that are relevant, and the defaults that apply, depend on the usage; for example, attribute names must be strings.  
  
 An instance of Analysis Services accepts only a certain set of data types. Use of other data types results in an error, rather than an implicit conversion to one of the valid types.  
  
 The following table lists elements of type **DataItem**.  
  
|Parent Element|Element of type **DataItem**|Comments|  
|--------------------|----------------------------------|--------------|  
|[AttributeTranslation](attributetranslation-data-type-assl.md)|[CaptionColumn](../objects/captioncolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md) or [AttributeBinding](attributebinding-data-type-assl.md)|  
|[DimensionAttribute](dimensionattribute-data-type-assl.md)|[CustomRollupColumn](../objects/customrollupcolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md) or [AttributeBinding](attributebinding-data-type-assl.md)|  
|[DimensionAttribute](dimensionattribute-data-type-assl.md)|[CustomRollupPropertiesColumn](../objects/customrolluppropertiescolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md) or [AttributeBinding](attributebinding-data-type-assl.md)|  
|[DimensionAttribute](dimensionattribute-data-type-assl.md)|[KeyColumn](../objects/keycolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md), [AttributeBinding](attributebinding-data-type-assl.md) or [TimeBinding](timebinding-data-type-assl.md)|  
|[DimensionAttribute](dimensionattribute-data-type-assl.md)|[NameColumn](../objects/namecolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md) or [AttributeBinding](attributebinding-data-type-assl.md)|  
|[DimensionAttribute](dimensionattribute-data-type-assl.md)|[SkippedLevelsColumn](../objects/skippedlevelscolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md) or [AttributeBinding](attributebinding-data-type-assl.md)|  
|[DimensionAttribute](dimensionattribute-data-type-assl.md)|[UnaryOperatorColumn](../objects/unaryoperatorcolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md) or [AttributeBinding](attributebinding-data-type-assl.md)|  
|[Measure](../objects/measure-element-assl.md)|[Source](../properties/source-element-binding-assl.md)|**Source** element of the **DataItem** must be of type [RowBinding](rowbinding-data-type-assl.md), [ColumnBinding](columnbinding-data-type-assl.md), [MeasureBinding](measurebinding-data-type-assl.md), or [CubeDimensionBinding](cubedimensionbinding-data-type-assl.md)|  
|[MeasureGroupAttribute](measuregroupattribute-data-type-assl.md)|[KeyColumn](../objects/keycolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md), [AttributeBinding](attributebinding-data-type-assl.md) or [InheritedBinding](inheritedbinding-data-type-assl.md)|  
|[ScalarMiningStructureColumn](scalarminingstructurecolumn-data-type-assl.md)|[KeyColumn](../objects/keycolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md)|  
|[ScalarMiningStructureColumn](scalarminingstructurecolumn-data-type-assl.md)|[NameColumn](../objects/namecolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md)|  
|[TableMiningStructureColumn](tableminingstructurecolumn-data-type-assl.md)|[ForeignKeyColumn](../objects/foreignkeycolumn-element-assl.md)|**Source** element of the **DataItem** must be of type [ColumnBinding](columnbinding-data-type-assl.md)|  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DataItem>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
