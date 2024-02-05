---
title: "HoldoutSeed Element | Microsoft Docs"
description: Learn about the HoldoutSeed property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# HoldoutSeed Element

  Specifies the seed for a repeatable holdout partition that contains the test set of a [MiningStructure](../objects/miningstructure-element-assl.md) element. This seed ensures that the model content remains the same during reprocessing. If unspecified or set to 0,Analysis Services creates a seed by using a hashing algorithm on the name of the mining structure.  
  
## Syntax  
  
```xml  
  
<MiningStructure>  
   ...  
   <ddl100_100:HoldoutSeed>...</ddl100_100:HoldoutSeed>  
   ...  
</MiningStructure>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Long|  
|Default value|0|  
|Cardinality|0-1: Optional element that can occur one time and one time only.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[MiningStructure](../objects/miningstructure-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 When you first create a mining structure, the ID and the name are the same. However, you can change the name of the mining structure. Therefore, if you want to ensure that the partition is repeatable, you should not rely on the seed created by the name, but should explicitly set a seed.  
  
 Additionally, when you create a copy of a mining structure by using the **EXPORT** statement,Analysis Services will retain the name for the new mining structure but will automatically generate a new ID. Therefore, it is possible to have two mining structures that share the same name but have different IDs. Any two mining structures that have the same name will have the same seed. However, as the partitioning of the data also depends on the source data, the actual contents of the partitions in each structure may be different.  
  
 The new properties **HoldoutMaxCases**, **HoldoutMaxPercent**, **HoldoutSeed**, or **HoldoutActualSize** are available only in SQL Server 2008 and later versions. Therefore, you must prefix these properties with the new namespace as shown in the syntax description, orAnalysis Services will return an error.  
  
 **Note** In SQL Server 2005,Analysis Services did not support the use of holdout partitions on a mining structure. Therefore,Analysis Services Scripting Language (ASSL) statements that contain the holdout parameters **HoldoutMaxCases**, **HoldoutMaxPercent**, **HoldoutSeed**, or **HoldoutActualSize** cannot be used in SQL Server 2005. If you use one of these holdout parameters in an ASSL statement in SQL Server 2005,Analysis Services will return an error.  
  
 The element that corresponds to the parent of **HoldoutSeed** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningStructure>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)   
 [HoldoutActualSize Element](holdoutactualsize-element.md)   
 [HoldoutMaxPercent Element](holdoutmaxpercent-element.md)   
 [HoldoutMaxCases Element](holdoutmaxcases-element.md)  
  
  
