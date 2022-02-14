---
title: "PartitionBinding Data Type (ASSL) | Microsoft Docs"
description: Learn about the PartitionBinding data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# PartitionBinding Data Type (ASSL)

  Defines a derived data type that represents a binding to a [Partition](../objects/partition-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<PartitionBinding>  
   <DatabaseID>...</DatabaseID>  
   <CubeID>...</CubeID>  
   <PartitionID>...</PartitionID>  
   <Source>...</Source>  
</PartitionBinding>  
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
|Child elements|[CubeID](../../xmla/xml-elements-properties/cubeid-element-xmla.md), [DatabaseID](../../xmla/xml-elements-properties/databaseid-element-xmla.md), [PartitionID](../../xmla/xml-elements-properties/partitionid-element-xmla.md), [Source](../properties/source-element-binding-assl.md)|  
|Derived elements|See [Binding](binding-data-type-assl.md)|  
  
## Remarks  
 For additional information about the **Binding** type, including tables of Analysis Services Scripting Language (ASSL) objects of the **Binding** type and the inheritance hierarchy of **Binding** types, see [Binding Data Type &#40;ASSL&#41;](binding-data-type-assl.md).  

