---
title: "TargetType Element (ASSL) | Microsoft Docs"
description: Learn about the TargetType property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: kfollis
ms.author: kfollis

---
# TargetType Element (ASSL)

  Identifies the item type of the item identified in the [Target](target-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<Action>  
   ...  
   <TargetType>...</TargetType>  
   ...  
</Action>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent element|[Action](../objects/action-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Cube*|The target of the action is a cube.|  
|*Cells*|The target of the action is a subcube.|  
|*Set*|The target of the action is a set.|  
|*Hierarchy*|The target of the action is a hierarchy.|  
|*Level*|The target of the action is a level.|  
|*DimensionMembers*|The target of the action is the members of a dimension.|  
|*HierarchyMembers*|The target of the action is the members of a hierarchy.|  
|*LevelMembers*|The target of the action is the members of a level.|  
|*AttributeMembers*|The target of the action is the members of an attribute.|  
  
 The enumeration that corresponds to the allowed values for **TargetType** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.ActionTargetType>.  
  
 The element that corresponds to the parent of **TargetType** in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.Action>.  
  
## See Also  
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
