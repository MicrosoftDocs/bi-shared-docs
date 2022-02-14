---
title: "DbSchemaName Element (ASSL) | Microsoft Docs"
description: Learn about the DbSchemaName property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# DbSchemaName Element (ASSL)

  Contains the name of the schema used by the parent element in the table identified by the [DbTableName](dbtablename-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<TableBinding> <!-- or TableNotification -->  
   ...  
   <DbSchemaName>...</DbSchemaName>  
   ...  
</TableBinding>  
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
|Parent element|[TableBinding](../data-type/tablebinding-data-type-assl.md), [TableNotification](../objects/tablenotification-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **DbSchemaName** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.TableBinding> and <xref:Microsoft.AnalysisServices.TableNotification>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
