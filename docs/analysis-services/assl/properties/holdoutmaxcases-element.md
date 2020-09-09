---
title: "HoldoutMaxCases Element | Microsoft Docs"
description: Learn about the HoldoutMaxCases property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
---
# HoldoutMaxCases Element

  Specifies the maximum number of cases in the data source to be used for the holdout partition that contains the test set of a [MiningStructure](../objects/miningstructure-element-assl.md) element. The remaining cases in the data set are used for training. A value of 0 indicates that there is no limit to the number of cases that can be held out as the test set.  
  
## Syntax  
  
```xml  
  
<MiningStructure>  
   ...  
   <ddl100_100:HoldoutMaxCases>...</ddl100_100:HoldoutMaxCases>  
   ...  
</MiningStructure>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Integer greater than 0.|  
|Default value|0|  
|Cardinality|0-1: Optional element that can occur one time and one time only.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[MiningStructure](../objects/miningstructure-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 If you specify values for both **HoldoutMaxPercent** and **HoldoutMaxCases**, the algorithm limits the test set to the smaller of the two values.  
  
 If **HoldoutMaxCases** is set to the default of 0, and a value has not been set for **HoldoutMaxPercent**, the algorithm uses the entire data set for training.  
  
 The new properties **HoldoutMaxCases**, **HoldoutMaxPercent**, **HoldoutSeed**, or **HoldoutActualSize** are available only in SQL Server 2008 and later versions. Therefore, you must prefix these properties with the new namespace as shown in the syntax description, orAnalysis Services will return an error.  
  
> [!NOTE]  
>  In SQL Server 2005,Analysis Services did not support the use of holdout partitions on a mining structure. Therefore,Analysis Services Scripting Language (ASSL) statements that contain one of the holdout parameters, **HoldoutMaxCases**, **HoldoutMaxPercent**, **HoldoutSeed**, or **HoldoutActualSize**, cannot be used in SQL Server 2005. If you use one of these holdout parameters in an ASSL statement in SQL Server 2005,Analysis Services will return an error.  
  
 The element that corresponds to the parent of **HoldoutMaxCases** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningStructure>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)   
 [HoldoutMaxPercent Element](holdoutmaxpercent-element.md)   
 [HoldoutSeed Element](holdoutseed-element.md)   
 [HoldoutActualSize Element](holdoutactualsize-element.md)  
  
  
