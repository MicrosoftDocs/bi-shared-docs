---
title: "DbTableName Element (ASSL) | Microsoft Docs"
description: Learn about the DbTableName property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# DbTableName Element (ASSL)

  Contains the name of the table to which the parent element is bound.  
  
## Syntax  
  
```xml  
  
<TableBinding> <!-- or TableNotification -->  
   ...  
   <DbTableName>...</DbTableName>  
   ...  
</TableBinding>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String|  
|Default value|None|  
|Cardinality|1-1: Required element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[TableBinding](../data-type/tablebinding-data-type-assl.md), [TableNotification](../objects/tablenotification-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **DbTableName** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.TableBinding> and <xref:Microsoft.AnalysisServices.TableNotification>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
