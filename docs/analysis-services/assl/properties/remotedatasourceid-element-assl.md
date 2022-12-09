---
title: "RemoteDatasourceID Element (ASSL) | Microsoft Docs"
description: Learn about the RemoteDatasourceID property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: owend

ms.topic: reference
author: minewiskan
ms.author: owend

---
# RemoteDatasourceID Element (ASSL)

  Specifies the identifier (ID) of the OLAP data source that points to the instance of Analysis Services that stores the remote partition.  
  
## Syntax  
  
```xml  
  
<Partition>  
      ...  
   <RemoteDatasourceID>...</RemoteDatasourceID>  
   ...  
</Partition>  
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
|Parent element|[Partition](../objects/partition-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 If **RemoteDatasourceID** is null, then the partition is local.  
  
 The element that corresponds to the parent of **RemoteDatasourceID** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Partition>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
