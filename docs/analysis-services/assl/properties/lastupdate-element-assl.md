---
title: "LastUpdate Element (ASSL) | Microsoft Docs"
description: Learn about the LastUpdate property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend

---
# LastUpdate Element (ASSL)

  Contains a read-only timestamp that indicates the last time that the associated [Database](../objects/database-element-assl.md) or any of the major objects that the database contains were altered.  
  
## Syntax  
  
```xml  
  
<Database> <!-- or one of the elements that are listed in the Element Relationships table -->  
   ...  
   <LastUpdate>...</LastUpdate>  
   ...  
</Assembly>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|DateTime|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Database](../objects/database-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **LastUpdate** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.Dimension>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
