---
title: "FoldingParameters Element (ASSL) | Microsoft Docs"
description: Learn about the FoldingParameters property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# FoldingParameters Element (ASSL)

  Specifies the parameters used by theAnalysis Services server when it performs cross-validation of mining models.  
  
> [!NOTE]  
>  These parameters are for internal use only. The information provided here is for reference only.  
  
## Syntax  
  
```xml  
  
<MiningModel>  
   ...  
   <ddl100_100:FoldingParameters>...  
      <ddl100_100:FoldIndex>...</ddl100_100:FoldIndex>  
      <ddl100_100:FoldCount>...</ddl100_100:FoldCount>  
      <ddl100_100:MaxCases>...</ddl100_100:MAxCases>  
      <ddl100_100:FoldTargetAttribute>...</ddl100_100:FoldTargetAttribute  
...</ddl100_100:FoldingParameters>  
</MiningStructure>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|*FoldIndex*|Integer that indicates the starting position of the partition that is used for cross-validation.|  
|*FoldCount*|Integer that indicates the number of partitions in the model after cross-validation.|  
|*MaxCases*|Integer that indicates how many model cases are used for cross-validation.<br /><br /> A value of 0 indicates that all cases are used.|  
|*FoldTargetAttribute*|String that indicates the ID of the model column that contains the predictable attribute.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[MiningModel](../objects/miningmodel-element-assl.md)|  
|Child elements|*FoldIndex*<br /><br /> *FoldCount*<br /><br /> *MaxCases*<br /><br /> *FoldTargetAttribute*|  
  
## Remarks  
 These properties are for internal use only, and are not supported for use in DDL statements.  