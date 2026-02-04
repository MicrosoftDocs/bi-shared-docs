---
title: "StorageLocation Element (ASSL) | Microsoft Docs"
description: Learn about the StorageLocation property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: eur

ms.topic: reference
author: eric-urban
ms.author: eur

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
  
  
