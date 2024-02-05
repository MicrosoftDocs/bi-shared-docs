---
title: "Configure Attribute Relationship Properties | Microsoft Docs"
description: See a table that lists and describes the properties of an attribute relationship, like Name, Visibility, and RelationshipType.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Attribute Relationships - Configure Attribute Properties
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  The following table lists and describes the properties of an attribute relationship.  
  
|Property|Description|  
|--------------|-----------------|  
|Attribute|Contains the name of the attribute.|  
|Cardinality|Indicates the cardinality of the relationship. Values are Many, for a many to one relationship, or One, for a one to one relationship. Default value is Many. In [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], the cardinality property has no effect - its use is reserved for a future implementation.|  
|Name|Contains the friendly name of the attribute.|  
|RelationshipType|Indicates whether member relationships change over time. Values are Rigid, which means that relationships between members do not change over time, or Flexible, which means that relationships between members change over time. Default is Flexible. If you define a relationship as flexible, aggregations are dropped and recomputed as part of an incremental update (they will not be dropped if only new members are added). If you define a relationship as rigid, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] retains aggregations when the dimension is incrementally updated. If a relationship that is defined as rigid actually changes, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] generates an error during incremental processing. Specifying the appropriate relationships and relationship properties increases query and processing performance.|  
|Visible|Determines the visibility of the attribute relationship. Values are True or False. Default is True.|  
  
  
