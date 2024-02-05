---
title: "DiscretizationMethod Element (ASSL) | Microsoft Docs"
description: Learn about the DiscretizationMethod property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# DiscretizationMethod Element (ASSL)

  Defines the method to be used for discretization.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute> <!-- or ScalarMiningStructureColumn -->  
   ...  
   <DiscretizationMethod>...</DiscretizationMethod>  
   ...  
</DimensionAttribute>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*None*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md), [ScalarMiningStructureColumn](../data-type/scalarminingstructurecolumn-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of the **DiscretizationMethod** element determines how values for the **DimensionAttribute** or **ScalarMiningStructureColumn** are discretized, or organized into a specific set of groups. 
  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Automatic*|Equivalent to the AUTOMATIC discretization method for mining structure columns.|  
|*EqualAreas*|Equivalent to the EQUAL_AREAS discretization method for mining structure columns.|  
|*Clusters*|Equivalent to the CLUSTERS discretization method for mining structure columns.|  
|*Thresholds*|Equivalent to the THRESHOLDS discretization method for mining structure columns.|  
|*EqualRanges*|Equivalent to the EQUAL_RANGES discretization method for mining structure columns.|  
  
 The enumeration corresponding to the allowed values for **DiscretizationMethod** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DiscretizationMethod>.  

  
