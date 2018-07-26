---
title: "StorageLocation Element (ASSL) | Microsoft Docs"
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
# StorageLocation Element (ASSL)

  Contains the file system storage location for the contents of the parent element.  
  
## Syntax  
  
```xml  
  
<Cube><!-- or MeasureGroup, Partition -->  
      ...  
   <StorageLocation>...</StorageLocation>  
   ...  
</Cube>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|See the table below.|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
|Ancestor or Parent|Default Value|  
|------------------------|-------------------|  
|[Cube](../objects/cube-element-assl.md)|None|  
|[MeasureGroup](../objects/measuregroup-element-assl.md)|Value of **StorageLocation** from the **Cube** parent element.|  
|[Partition](../objects/partition-element-assl.md)|Value of **StorageLocation** from the **MeasureGroup** parent element.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Cube](../objects/cube-element-assl.md), [MeasureGroup](../objects/measuregroup-element-assl.md), [Partition](../objects/partition-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **StorageLocation** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.Cube>, <xref:Microsoft.AnalysisServices.MeasureGroup>, and <xref:Microsoft.AnalysisServices.Partition>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
