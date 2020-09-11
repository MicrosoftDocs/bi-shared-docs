---
title: "MasterDatasourceID Element (ASSL) | Microsoft Docs"
description: Learn about the MasterDatasourceID property element in the Analysis Services Scripting Language (ASSL) schema.
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
# MasterDatasourceID Element (ASSL)

  Contains the master data source identifier (ID) for a [Database](../objects/database-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Database>  
   ...  
   <MasterDatasourceID>...</MasterDatasourceID>  
   ...  
</Database>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Database](../objects/database-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 For databases on remote instances of Analysis Services that contain remote partitions, the **MasterDatasourceID** element contains the data source ID of the data source used to identify the master instance ofAnalysis Services that manages the remote partitions.  
  
 The element that corresponds to the parent of **MasterDatasourceID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Database>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
