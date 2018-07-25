---
title: "MdxScript Element (ASSL) | Microsoft Docs"
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# MdxScript Element (ASSL)

  Contains information about a Multidimensional Expressions (MDX) script that is associated with a [Cube](objects/cube-element-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MdxScripts>  
   <MdxScript>  
      <Name>...</Name>  
      <ID>...</ID>  
      <Description>...</Description>  
      <CreatedTimestamp>...</CreatedTimestamp>  
      <LastSchemaUpdate>...</LastSchemaUpdate>  
      <Annotations>...</Annotations>  
      <Commands>...</Commands>  
      <DefaultScript>...</DefaultScript>  
      <CalculationProperties>...</CalculationProperties>  
   </MdxScript>  
</MdxScripts>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MdxScripts](collections/mdxscripts-element-assl.md)|  
|Child elements|[Annotations](collections/annotations-element-assl.md), [CalculationProperties](collections/calculationproperties-element-assl.md), [Commands](collections/commands-element-assl.md), [CreatedTimestamp](properties/createdtimestamp-element-assl.md), [DefaultScript](properties/defaultscript-element-assl.md), [Description](properties/description-element-assl.md), [ID](properties/id-element-assl.md), [LastSchemaUpdate](properties/lastschemaupdate-element-assl.md), [Name](properties/name-element-assl.md)|  
  
## Remarks  
 A script's **DefaultScript** element is set to **True** by default. Setting **DefaultScript** to **True** for a particular script sets **DefaultScript** to **False** for all other scripts.  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MdxScript>.  
  
## See Also  
 [Objects &#40;ASSL&#41;](objects/objects-assl.md)  
  
  
