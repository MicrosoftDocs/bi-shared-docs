---
title: "AllowDrillThrough Element (ASSL) | Microsoft Docs"
description: Learn about the AllowDrillThrough property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# AllowDrillThrough Element (ASSL)

  Determines whether drillthrough is permitted on the parent element.  
  
## Syntax  
  
```xml  
  
<MiningModel> <!-- or MiningModelPermission -->  
<!-- or MiningStructurePermission -->   ...  
   <AllowDrillThrough>...</AllowDrillThrough>  
   ...  
</MiningModel>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|Boolean|  
|Default value|**False**|  
|Cardinality|0-1: Optional element that can occur one time and only one time.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MiningModel Element](../objects/miningmodel-element-assl.md), [MiningModelPermission](../objects/miningmodelpermission-element-assl.md), [MiningStructurePermission](../objects/miningstructurepermission-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The elements that correspond to the parents of **AllowDrillThrough** in the Analysis Management Objects (AMO) object model are <xref:Microsoft.AnalysisServices.MiningModel>, <xref:Microsoft.AnalysisServices.MiningModelPermission>, and <xref:Microsoft.AnalysisServices.MiningStructurePermission>.  
  
## Drillthrough on Mining Structures  
 In SQL Server, you can define **AllowDrillthrough** permissions for mining structures as well as mining models. When you assign this permission to a role, any member of that role can query the data mining model, and return structure columns that were not included in the model. For example, you create a model that uses only these columns: customer key, customer income, and customer purchases. If you enable drillthrough on the model, users can return information in other columns of the mining structure, such as customer e-mails or names.  
  
 Therefore, to protect sensitive data, use caution when you add columns to the mining structure. Also, grant **AllowDrillthrough** permission on a structure only when it is required.  
  
 To drill through to structure columns, use a query with one of the following forms:  
  
 `SELECT * FROM <structure>.CASES`  
  
 or  
  
 `SELECT StructureColumn('<structure-column-name>') FROM <model>.CASES`  
  
## See Also  
 [Role Element &#40;ASSL&#41;](../objects/role-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
