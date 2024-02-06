---
title: "ProcessingQuery Element (ASSL) | Microsoft Docs"
description: Learn about the ProcessingQuery property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# ProcessingQuery Element (ASSL)

  Contains the parameterized text of the query to execute for notification of incremental processing status.  
  
## Syntax  
  
```xml  
  
<IncrementalProcessingNotification>  
   ...  
   <ProcessingQuery>...</ProcessingQuery>  
   ...  
</IncrementalProcessingNotification>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[IncrementalProcessingNotification](../objects/incrementalprocessingnotification-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The table in the [DataSourceView](../objects/datasourceview-element-assl.md) that is referenced by the **ProcessingQuery** is identified by the sibling element, [TableID](tableid-element-assl.md).  
  
 The element that corresponds to the parent of **ProcessingQuery** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.IncrementalProcessingNotification>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
