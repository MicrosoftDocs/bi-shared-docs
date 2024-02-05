---
title: "AllowedRowsExpression Element (ASSL) | Microsoft Docs"
description: Learn about the AllowedRowsExpression property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# AllowedRowsExpression Element (ASSL)

  Contains a Data Analysis expression (DAX), of Boolean type, which defines the contents of the parent element.  
  
## Syntax  
  
```xml  
  
<CellPermission> <!-- or StandardAction -->  
   ...  
   <Expression>...</Expression>  
   ...  
</CellPermission>  
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
|Parent elements|[CellPermission](../objects/cellpermission-element-assl.md), [StandardAction](../data-type/standardaction-data-type-assl.md)|  
|Child elements|None|  
  
## Remarks  
 For the **CellPermission** element, the **Expression** element contains a logical MDX expression that identifies cells applicable to the rights indicated by the [Access](access-element-assl.md) element of the **CellPermission** element. If the value of an **Expression** element for a **CellPermission** element is empty, the **CellPermission** element is ignored.  
  
 For the **StandardAction** element, the **Expression** element contains an MDX expression that represents the contents of the action. If the value of an **Expression** element for a **StandardAction** element is empty, the **StandardAction** element is ignored.  
  
 The elements that correspond to the parents in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.CellPermission> and <xref:Microsoft.AnalysisServices.StandardAction>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
