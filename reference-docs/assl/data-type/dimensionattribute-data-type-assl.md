---
title: "DimensionAttribute Data Type (ASSL) | Microsoft Docs"
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
# DimensionAttribute Data Type (ASSL)

  Defines a primitive data type that represents an attribute in a dimension.  
  
## Syntax  
  
```xml  
  
<DimensionAttribute>  
   <Name>...</Name>  
   <ID>...</ID>  
   <Description>...</Description>  
   <Type>...</Type>  
   <Usage>...</Usage>  
   <Source>...</Source>  
   <EstimatedCount>...</EstimatedCount>  
   <KeyColumns>...</KeyColumns>  
   <NameColumn>...</NameColumn>  
   <ValueColumn>...</ValueColumn>  
   <Translations>...</Translations>  
   <AttributeRelationships>...</AttributeRelationships>  
   <DiscretizationMethod>...</DiscretizationMethod>  
   <DiscretizationBucketCount>...</DiscretizationBucketCount>  
   <RootMemberIf>...</RootMemberIf>  
   <OrderBy>...</OrderBy>  
   <DefaultMember>...</DefaultMember>  
   <OrderByAttributeID>...</OrderByAttributeID>  
   <SkippedLevelsColumn>...</SkippedLevelsColumn>  
   <NamingTemplate>...</NamingTemplate>  
   <MembersWithData>...</MembersWithData>  
   <MembersWithDataCaption>...</MembersWithDataCaption>  
   <NamingTemplateTranslations>...</NamingTemplateTranslations>  
   <CustomRollupColumn>...</CustomRollupColumn>  
   <CustomRollupPropertiesColumn>...</CustomRollupPropertiesColumn>  
   <UnaryOperatorColumn>...</UnaryOperatorColumn>  
   <AttributeHierarchyOrdered>...</AttributeHierarchyOrdered>  
   <MemberNamesUnique>...</MemberNamesUnique>  
   <IsAggregatable>...</IsAggregatable>  
   <AttributeHierarchyEnabled>...</AttributeHierarchyEnabled>  
   <AttributeHierarchyOptimizedState>...</AttributeHierarchyOptimizedState>  
   <AttributeHierarchyVisible>...</AttributeHierarchyVisible>  
   <AttributeHierarchyDisplayFolder>...</AttributeHierarchyDisplayFolder>  
   <KeyUniquenessGuarantee>...<KeyUniquenessGuarantee>  
   <InstanceSelection>...</InstanceSelection>  
   <Annotations>...</Annotations>  
</DimensionAttribute>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|None|  
|Child elements|[Annotations](collections/annotations-element-assl.md), [AttributeHierarchyDisplayFolder](properties/attributehierarchydisplayfolder-element-assl.md), [AttributeHierarchyEnabled](properties/attributehierarchyenabled-element-assl.md), [AttributeHierarchyOptimizedState](properties/attributehierarchyoptimizedstate-element-assl.md), [AttributeHierarchyOrdered](properties/attributehierarchyordered-element-assl.md), [AttributeHierarchyVisible](properties/attributehierarchyvisible-element-assl.md), [AttributeRelationships](collections/attributerelationships-element-assl.md), [CustomRollupColumn](objects/customrollupcolumn-element-assl.md), [CustomRollupPropertiesColumn](objects/customrolluppropertiescolumn-element-assl.md), [DefaultMember](properties/defaultmember-element-assl.md), [Description](properties/description-element-assl.md), [DiscretizationBucketCount](properties/discretizationbucketcount-element-assl.md), [DiscretizationMethod](properties/discretizationmethod-element-assl.md), [EstimatedCount](properties/estimatedcount-element-assl.md), [ID](properties/id-element-assl.md), [InstanceSelection](properties/instanceselection-element-assl.md), [IsAggregatable](properties/isaggregatable-element-assl.md), [KeyColumns](collections/keycolumns-element-assl.md), [KeyUniquenessGuarantee](properties/keyuniquenessguarantee-element-assl.md), [MemberNamesUnique](properties/membernamesunique-element-assl.md), [MembersWithData](properties/memberswithdata-element-assl.md), [MembersWithDataCaption](properties/memberswithdatacaption-element-assl.md), [Name](properties/name-element-assl.md), [NameColumn](objects/namecolumn-element-assl.md), [NamingTemplate](properties/namingtemplate-element-assl.md), [NamingTemplateTranslations](collections/namingtemplatetranslations-element-assl.md), [OrderBy](properties/orderby-element-assl.md), [OrderByAttributeID](properties/orderbyattributeid-element-assl.md), [RootMemberIf](properties/rootmemberif-element-assl.md), [SkippedLevelsColumn](objects/skippedlevelscolumn-element-assl.md), [Source](properties/source-element-binding-assl.md), [Translations](collections/translations-element-assl.md), [Type](properties/type-element-dimensionattribute-assl.md), [UnaryOperatorColumn](objects/unaryoperatorcolumn-element-assl.md), [Usage](properties/usage-element-dimensionattribute-assl.md), [ValueColumn](objects/valuecolumn-element-assl.md)|  
|Derived elements|[Attribute](objects/attribute-element-assl.md) ([Attributes](collections/attributes-element-assl.md) collection of [Dimension](objects/dimension-element-assl.md))|  
  
## Remarks  
 The following restrictions apply when running the service in DeploymentMode configuration property values of 1 and 2 (SharePoint and Tabular modes, used to run [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] and tabular model databases):  
  
-   Usage element only accepts KEY or REGULAR values.  
  
-   IsAggregatable element cannot be false.  
  
-   OrderBy element only accepts KEY or PROPERTYKEY values.  
  
-   A calculated column cannot be a primary key in the table.  
  
-   A calculated column cannot contain DataSize in the binding.  
  
-   For each calculated column a syntax validation is performed before saving the attribute definition.  
  
-   For AttributeRelationships, RelationshipType must be set to the value, Flexible.  
  
-   The attribute ‘RowNumber’, identified by ‘RowNumber’, must have the type integer.  
  
-   Only the attribute ‘RowNumber’ can have KeyBinding of type RowNumberBinding.  
  
-   All attributes other than ‘RowNumber’ must have a Cardinality of one in relation to the key, unless the attribute itself is the key.  
  
-   When the column specified by OrderBy is also the PropertyKey, the OrderByAttributeId cannot point to the row number column.  
  
-   Attributes used as keys should be related to all other attributes; other types of relationships are not supported.  
  
-   The NullProcessing element cannot be set to ‘UnknownMember’.  
  
-   Bindings cannot be set to ‘Value’.  
  
 The following elements are unsupported when running the service in DeploymentMode configuration property values of 1 and 2 (SharePoint and Tabular modes, used to run [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] and tabular model databases):  
  
-   AttributeHierarchyOptimizedState  
  
-   CustomRollupColumn  
  
-   CustomRollupPropertiesColumn  
  
-   DefaultMember  
  
-   DiscretizationBucketCount  
  
-   DiscretizationMethod  
  
-   SkippedLevelsColumn  
  
-   Source  
  
-   UnaryOperatorColumn  
  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.DimensionAttribute>.  
  
## See Also  
 [Analysis Services Scripting Language XML Data Types &#40;ASSL&#41;](data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
