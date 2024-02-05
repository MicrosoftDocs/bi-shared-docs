---
title: "Blocks Element (ASSL) | Microsoft Docs"
description: Learn about the Blocks collection element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Blocks Element (ASSL)

  Contains the collection of blocks of binary data that represent the binary contents of a [ClrAssemblyFile](../data-type/clrassemblyfile-data-type-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Data xsi:type="DataBlock">  
   ...  
   <Blocks>  
      <Block>...</Block>  
   </Blocks>  
   ...  
</File>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Data](../objects/data-element-assl.md) of type [DataBlock](../data-type/datablock-data-type-assl.md)|  
|Child elements|[Block](../objects/block-element-assl.md)|  
  
## Remarks  
 The element that corresponds to the parent of **Blocks** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ClrAssemblyFile>.  
