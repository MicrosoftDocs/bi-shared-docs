---
title: "Attribute Element (XMLA) | Microsoft Docs"
description: Learn how the Attribute element defines or filters a member in an attribute on which a parent Insert, Update, or Drop command performs.
ms.date: 01/05/2020
ms.service: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Attribute Element (XMLA)

  Defines or filters a member in an attribute on which a parent [Insert](../xml-elements-commands/insert-element-xmla.md), [Update](../xml-elements-commands/update-element-xmla.md), or [Drop](../xml-elements-commands/drop-element-xmla.md) command performs.  
  
## Syntax  
  
```xml  
  
<Attributes>  
   ...  
   <Attribute>  
      <AttributeName>...</AttributeName>  
      <Keys>...</Keys>  
      <!-- The following elements are included only for attributes contained in the Attributes element of a parent Insert or Update command -->  
      <Name>...</Name>  
      <Translations>...</Translations>  
      <CustomRollup>...</CustomRollup>  
      <CustomRollupProperties>...</CustomRollupProperties>  
      <UnaryOperator>...</UnaryOperator>  
      <SkippedLevels>...</SkippedLevels>  
   </Attribute>  
   ...  
</Attributes>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Attributes](../xml-elements-properties/attributes-element-xmla.md)|  
|Child elements|See the table below.|  
  
|Ancestor or Parent|Child Element|  
|------------------------|-------------------|  
|[Drop](../xml-elements-commands/drop-element-xmla.md), [Where](../xml-elements-properties/where-element-xmla.md)|[AttributeName](../xml-elements-properties/attributename-element-xmla.md), [Keys](../xml-elements-properties/keys-element-xmla.md)|  
|[Insert](../xml-elements-commands/insert-element-xmla.md), [Update](../xml-elements-commands/update-element-xmla.md)|[AttributeName](../xml-elements-properties/attributename-element-xmla.md), [CustomRollup](../xml-elements-properties/customrollup-element-xmla.md), [CustomRollupProperties](../xml-elements-properties/customrollupproperties-element-xmla.md), [Keys](../xml-elements-properties/keys-element-xmla.md), [Name](../xml-elements-properties/name-element-xmla.md), [SkippedLevels](../xml-elements-properties/skippedlevels-element-xmla.md), [Translations](../xml-elements-properties/translations-element-xmla.md), [UnaryOperator](../xml-elements-properties/unaryoperator-element-xmla.md)|  
  
## Remarks  
 The **Attribute** element defines the attribute member that is inserted, updated, or deleted, respectively, by the **Insert**, **Update**, or **Drop** command. As these commands can operate only on one attribute member at a time, the [Attributes](../xml-elements-properties/attributes-element-xmla.md) collection of the **Insert**, **Update**, and **Drop** commands can contain only one **Attribute** element. However, the **Attributes** collection of the **Where** element for the **Drop** and **Update** commands can contain more than one **Attribute** element, so that you can filter the attributes to be dropped or updated in a write-enabled dimension.  
