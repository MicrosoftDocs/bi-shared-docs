---
title: "CurrentStorageMode Element (ASSL) | Microsoft Docs"
description: Learn about the CurrentStorageMode property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference

---
# CurrentStorageMode Element (ASSL)

  Determines the current storage mode for the parent element.  
  
## Syntax  
  
```xml  
  
<Dimension> <!-- or Partition -->  
   <CurrentStorageMode>...</CurrentStorageMode>  
</Dimension>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*ROLAP*|  
|Cardinality|0-1: Optional element that can occur once or not at all.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Dimension](../objects/dimension-element-assl.md), [Partition](../objects/partition-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The **CurrentStorageMode** element indicates the storage mode currently in use for proactive caching purposes, and applies to all attributes of the parent element.  
  
 The value of this element is limited to one of the strings in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*MOLAP*|The parent uses multidimensional OLAP (MOLAP) storage.|  
|*ROLAP*|The parent uses relational OLAP (ROLAP) storage.|  
|*HOLAP*|The parent uses hybrid OLAP (HOLAP) storage.<br /><br /> Note: This value is only valid for [Partition](../objects/partition-element-assl.md) parent elements.|  
  
 The enumeration corresponding to the allowed values **CurrentStorageMode** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.StorageMode>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
