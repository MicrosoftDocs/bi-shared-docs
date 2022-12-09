---
title: "MiningModelPermission Element (ASSL) | Microsoft Docs"
description: Learn about the MiningModelPermission object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 02/14/2022
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# MiningModelPermission Element (ASSL)

  Defines the permissions members of a [Role](../objects/role-element-assl.md) element have on an individual [MiningModel](../objects/miningmodel-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MiningModelPermissions>  
   <MiningModelPermission xsi:type="Permission">  
      <!-- The following elements extend Permission -->  
      <AllowDrillThrough>...</AllowDrillThrough>  
      <AllowBrowsing>...</AllowBrowsing>  
   </MiningModelPermission>  
</MiningModelPermissions>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|[Permission](../data-type/permission-data-type-assl.md)|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MiningModelPermissions](../collections/miningmodelpermissions-element-assl.md)|  
|Child elements|[AllowBrowsing](../properties/allowbrowsing-element-assl.md), [AllowDrillThrough](../properties/allowdrillthrough-element-assl.md)|  
  
## Remarks  
 You can enable drillthrough on mining structures by adding the **AllowDrillthrough** permission to the [MiningStructurePermissions](../collections/miningstructurepermissions-element-assl.md) collection. If **AllowDrillthrough** is enabled on both the mining structure and the mining model, any member of a role that has [AllowDrillThrough Element &#40;ASSL&#41;](../properties/allowdrillthrough-element-assl.md) permissions on the model can query the data mining model, and return structure columns that were not included in the model, by using the following syntax:  
  
```sql  
SELECT StructureColumn('<column name>') FROM <model>.CASES  
```  
  
 Therefore, to protect sensitive data or personal information, you should grant **AllowDrillthrough** permission on a mining model only when necessary. For more information, see [AllowDrillThrough Element &#40;ASSL&#41;](../properties/allowdrillthrough-element-assl.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningModelPermission>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](../objects/objects-assl.md)  
  
  
