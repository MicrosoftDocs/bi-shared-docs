---
title: "Technical Reference for BI Annotations to CSDL | Microsoft Docs"
ms.date: 07/26/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Technical Reference for BI Annotations to CSDL

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  This section lists the elements, attribute, and properties in CSDL that are used to represent Analysis Services tabular models. Some elements are new; others have been annotated or extended to support business intelligence modeling.  
  
 For an overview of tabular models and how the entities, relationships, and formulas are represented in CSDL, see [CSDL Annotations for Business Intelligence &#40;CSDLBI&#41;](csdl-annotations-for-business-intelligence-csdlbi.md).  
  
## Extended CSDL Elements: Complex Types

 The following elements of CSDL have been added or extended to support business intelligence data models, both tabular and multidimensional.  
  
-   [AssociationSet Element &#40;CSDLBI&#41;](associationset-element-csdlbi.md)  
  
-   [BaseProperty Element &#40;CSDLBI&#41;](baseproperty-element-csdlbi.md)  
  
-   [DefaultDetails Element &#40;CSDLBI&#41;](defaultdetails-element-csdlbi.md)  
  
-   [DisplayKey Element &#40;CSDLBI&#41;](displaykey-element-csdlbi.md)  
  
-   [EntityContainer Element &#40;CSDLBI&#41;](entitycontainer-element-csdlbi.md)  
  
-   [EntitySet Element &#40;CSDLBI&#41;](entityset-element-csdlbi.md)  
  
-   [EntityType Element &#40;CSDLBI&#41;](entitytype-element-csdlbi.md)  
  
-   [Hierarchy Element &#40;CSDLBI&#41;](hierarchy-element-csdlbi.md)  
  
-   [KPI Element &#40;CSDLBI&#41;](kpi-element-csdlbi.md)  
  
-   [KpiGoal Element &#40;CSDLBI&#41;](kpigoal-element-csdlbi.md)  
  
-   [KpiStatus Element &#40;CSDLBI&#41;](kpistatus-element-csdlbi.md)  
  
-   [Level Element &#40;CSDLBI&#41;](level-element-csdlbi.md)  
  
-   [Measure Element &#40;CSDLBI&#41;](measure-element-csdlbi.md)  
  
-   [Member Element &#40;CSDLBI&#41;](member-element-csdlbi.md)  
  
-   [MemberRef Element &#40;CSDLBI&#41;](memberref-element-csdlbi.md)  
  
-   [NavigationProperty Element &#40;CSDLBI&#41;](navigationproperty-element-csdlbi.md)  
  
-   [Property Element &#40;CSDLBI&#41;](property-element-csdlbi.md)  
  
-   [PropertyRef Element &#40;CSDLBI&#41;](propertyref-element-csdlbi.md)  
  
## Simple Type and Subtypes

 The following table lists some simple types and some minor complex types that are included in the definitions of the complex types listed above. The documentation for each simple type or subtype listed in the left-hand column is provided in the parent elements listed in the right-hand column.  
  
|Simple Type|Found in topic|  
|-----------------|--------------------|  
|Alignment|[BaseProperty Element &#40;CSDLBI&#41;](baseproperty-element-csdlbi.md)|  
|CompareOptions|[EntityContainer Element &#40;CSDLBI&#41;](entitycontainer-element-csdlbi.md)|  
|Contents|[EntityType Element &#40;CSDLBI&#41;](entitytype-element-csdlbi.md)|  
|ContextualNameRule|[Member Element &#40;CSDLBI&#41;](member-element-csdlbi.md)|  
|DefaultAggregationFunction|[Property Element &#40;CSDLBI&#41;](property-element-csdlbi.md)|  
|DirectQueryMode|[EntityContainer Element &#40;CSDLBI&#41;](entitycontainer-element-csdlbi.md)|  
|GroupingBehavior|[Property Element &#40;CSDLBI&#41;](property-element-csdlbi.md)|  
|MemberRefs|[MemberRef Element &#40;CSDLBI&#41;](memberref-element-csdlbi.md)|  
|PropertyRefs|[PropertyRef Element &#40;CSDLBI&#41;](propertyref-element-csdlbi.md)|  
|SortDirection|[BaseProperty Element &#40;CSDLBI&#41;](baseproperty-element-csdlbi.md)|  
|State|[AssociationSet Element &#40;CSDLBI&#41;](associationset-element-csdlbi.md)|  
|Stability|[Property Element &#40;CSDLBI&#41;](property-element-csdlbi.md)|  
|SortDirection|[BaseProperty Element &#40;CSDLBI&#41;](baseproperty-element-csdlbi.md)|  
  