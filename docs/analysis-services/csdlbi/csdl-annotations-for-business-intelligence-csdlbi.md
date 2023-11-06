---
title: "Conceptual Schema Definition Language for Business Intelligence Reference (Archived)| Microsoft Docs"
description: Learn about the CSDL schema, which supports data modeling, custom calculations, and enhanced presentation.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
---
# Conceptual Schema Definition Language (CSDLBI) Reference (Archived)

[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

## CSDLBI 1.0

 The initial set of additions to the CSDL schema to support  tabular models contained annotations in support of data modeling, custom calculations, and enhanced presentation:  
  
-   New elements and properties to support tabular models at the 1100 and 1103 compatibility levels. For example, a property was added to specify the type of database query used to populate the model.  
  
-   New properties and extensions to existing entities.  For example, the Association element was extended to support relationships.  
  
-   Visualization and navigation properties. For example, properties were added to support custom sorting fields, default images, and  
  
 ## CSDLBI 1.1
  
 This version of the CSDLBI schema includes additions in support of multidimensional databases (such as OLAP cubes). The new elements and properties are as follows:  
  
-   Support for dimensions as entities.  
  
-   Support for hierarchies.  
  
-   Exposes ROLAP partitions.  
  
-   Support for translations.  
  
-   Support for perspectives.

## See also

[CSDLBI Concepts](csdlbi-concepts.md)   
[Technical Reference for BI Annotations to CSDL](technical-reference-for-bi-annotations-to-csdl.md)