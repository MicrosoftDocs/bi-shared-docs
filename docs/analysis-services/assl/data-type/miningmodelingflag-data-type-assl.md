---
title: "MiningModelingFlag Data Type (ASSL) | Microsoft Docs"
description: Learn about the MiningModelingFlag data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# MiningModelingFlag Data Type (ASSL)

  Defines a primitive data type that represents the available modeling flags for a [ModelingFlag](../objects/modelingflag-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MiningModelingFlag>...</MiningModelingFlag>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|String (enumeration)|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|None|  
|Derived elements|[ModelingFlag](../objects/modelingflag-element-assl.md) ([ModelingFlags](../collections/modelingflags-element-assl.md) collection of [MiningModelColumn](miningmodelcolumn-data-type-assl.md) or [ScalarMiningStructureColumn](scalarminingstructurecolumn-data-type-assl.md))|  
  
## Remarks  
 The flag name may contain spaces. The natively-supported values are listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*MODEL_EXISTENCE_ONLY*|The column should be modeled as having two states, missing and nonmissing, regardless of the values in the column. This is particularly useful for columns in a nested table, where values are sparse across cases.|  
|*NOT NULL*|The column cannot accept NULL values.|  
|*REGRESSOR*|The column supplies regressor values for test cases.|  
  
 Additional provider-specific flags may be used if third-party OLE DB or data mining providers have been aggregated on the instance of Analysis Services.  
  
 A closely related element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningModelingFlags>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
