---
title: "MiningStructure Element (ASSL) | Microsoft Docs"
description: Learn about the MiningStructure object element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# MiningStructure Element (ASSL)

  Defines the structure for a set of mining models.  
  
## Syntax  
  
```xml  
  
<MiningStructures>  
   <MiningStructure>  
      <Name>...</Name>  
      <ID>...</ID>  
      <Description>...</<Description>  
      <Source>...</Source>  
      <CreatedTimestamp>...</<CreatedTimestamp>  
      <LastSchemaUpdate>...</LastSchemaUpdate>  
      <LastProcessed>...</LastProcessed>  
      <Translations>...</Translations>  
      <Language>...</Language>  
            <Collation>...</Collation>  
      <ErrorConfiguration>...</ErrorConfiguration>  
      <CacheMode>...</CacheMode>  
            <Columns>...</Columns>  
      <State>...</State>  
      <HoldoutActualSize>...</HoldoutActualSize>  
      <HoldoutMaxCases>...</HoldoutMaxCases>  
      <HoldoutMaxPercent>...</HoldoutMaxPercent>  
      <HoldoutSeed>...</HoldoutSeed>        
            <MiningStructurePermissions>...</<MiningStructurePermissions>  
            <MiningModels>...</MiningModels>  
            <Annotations>...</Annotations>  
   </MiningStructure>  
</MiningStructures>  
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
|Parent elements|[MiningStructures](../collections/miningstructures-element-assl.md)|  
|Child elements|[Annotations](../collections/annotations-element-assl.md), [CacheMode](../properties/cachemode-element-assl.md), [Collation](../properties/collation-element-assl.md), [Columns](../collections/columns-element-assl.md), [CreatedTimestamp](../properties/createdtimestamp-element-assl.md), [Description](../properties/description-element-assl.md), [ErrorConfiguration](../objects/errorconfiguration-element-assl.md),<br /><br /> [HoldoutActualSize](../properties/holdoutactualsize-element.md),<br /><br /> [HoldoutMaxCases](../properties/holdoutmaxcases-element.md),<br /><br /> [HoldoutMaxPercent](../properties/holdoutmaxpercent-element.md),<br /><br /> [HoldoutSeed](../properties/holdoutseed-element.md),<br /><br /> [ID](../properties/id-element-assl.md), [Language](../properties/language-element-assl.md), [LastProcessed](../properties/lastprocessed-element-assl.md), [LastSchemaUpdate](../properties/lastschemaupdate-element-assl.md), [MiningModels](../collections/miningmodels-element-assl.md), [MiningStructurePermissions](../collections/miningstructurepermissions-element-assl.md), [Name](../properties/name-element-assl.md), [Source](../properties/source-element-binding-assl.md), [State](../properties/state-element-assl.md), [Translations](../collections/translations-element-assl.md)|  
  
## Remarks  
 The mining structure defines the columns and the bindings. After defining a mining structure, you can use that structure to define many mining models. The mining structure, and each mining model it contains, can be processed independently.  
  
> [!NOTE]  
>  The holdout properties, **HoldoutMaxCases**, **HoldoutMaxPercent**, **HoldoutSeed**, and **HoldoutActualSize** enable you to define a partition on a mining structure that acts as the test set for all the mining models that are associated with the structure. SQL Server 2005 does not support these properties. Therefore, if you try to use these properties on an instance of SQL Server 2005,Analysis Services will return an error.  
  
## Drillthrough to Structure Columns  
 In SQL Server 2008, a new permission element has been added to the [MiningStructurePermissions Element &#40;ASSL&#41;](../collections/miningstructurepermissions-element-assl.md) collection. If you add **AllowDrillthrough** permission to both the [MiningStructurePermissions](../collections/miningstructurepermissions-element-assl.md) and [MiningModelPermission](../objects/miningmodelpermission-element-assl.md) collections, drillthrough is enabled from the mining model to the structure, in such a way that members of a role that has **AllowDrillthrough** permissions on the model can query the data mining model, and return structure columns that were not included in the model.  
  
 Therefore, to protect sensitive data or personal information, you should construct your data source view to mask sensitive information, and grant **AllowDrillthrough** permission on a mining structure only when necessary. For more information, see [AllowDrillThrough Element &#40;ASSL&#41;](../properties/allowdrillthrough-element-assl.md).  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.MiningStructure>.  
  
  
