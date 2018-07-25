---
title: "HoldoutActualSize Element | Microsoft Docs"
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
# HoldoutActualSize Element

  Indicates the actual size, after processing, of the holdout partition that contains the test set of a [MiningStructure](objects/miningstructure-element-assl.md) element. The remaining cases in the data set are used for training. This property is read-only.  
  
## Syntax  
  
```xml  
  
<MiningStructure>  
   ...  
   <ddl100_100:HoldoutActualSize>...</ddl100_100:HoldoutActualSize>  
   ...  
</MiningStructure  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Read-only integer value.|  
|Default value|Not applicable|  
|Cardinality|0-1: Optional element that can occur one time and only one time.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[MiningStructure](objects/miningstructure-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value for **HoldoutActualSize** depends on the source data, and on the values for [HoldoutMaxCases](properties/holdoutmaxcases-element.md), [HoldoutMaxPercent](properties/holdoutmaxpercent-element.md), and [HoldoutSeed](properties/holdoutseed-element.md). Therefore, the value for **HoldoutActualSize** is not available until afterAnalysis Services processes the mining structure.  
  
 The element that corresponds to the parent of **HoldoutActualSize** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningStructure>.  
  
> [!NOTE]  
>  In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)],Analysis Services did not support the use of holdout partitions on a mining structure. Therefore,Analysis Services Scripting Language (ASSL) statements that contain one of the holdout parameters, **HoldoutMaxCases**, **HoldoutMaxPercent**, **HoldoutSeed**, or **HoldoutActualSize**, cannot be used in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]. If you use one of these holdout parameters in an ASSL statement in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)],Analysis Services will return an error.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties/properties-assl.md)   
 [HoldoutMaxCases Element](properties/holdoutmaxcases-element.md)   
 [HoldoutMaxPercent Element](properties/holdoutmaxpercent-element.md)   
 [HoldoutSeed Element](properties/holdoutseed-element.md)  
  
  
