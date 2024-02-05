---
title: "Define Cube Dimension Properties | Microsoft Docs"
description: Learn about cube dimensions, instances of database dimensions within cubes that can be used in multiple cubes.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Define Cube Dimension Properties
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  A cube dimension is an instance of a database dimension within a cube. A database dimension can be used in multiple cubes, and multiple cube dimensions can be based on a single database dimension. The following table describes the properties of a cube dimension.  
  
|Property|Description|  
|--------------|-----------------|  
|**AllMemberAggregationUsage**|Controls how aggregations are designed by the Aggregation Designer in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. This property can have the following values:<br /><br /> **Full**: Every aggregation for the cube must include the All member.<br /><br /> **None**: No aggregation for the cube can include the All member. This is the default value.<br /><br /> **Unrestricted**: No restrictions are placed on the Aggregation Designer.<br /><br /> **Default**: The same functionality as Unrestricted.|  
|**Description**|Provides a descriptive name for the level.|  
|**DimensionID**|Contains the unique identifier (ID) of the database dimension.|  
|**HierarchyUniqueNameStyle**|Determines how unique names are generated for hierarchies that are contained within the cube dimension. This property can have the following values:<br /><br /> **IncludeDimensionName**:<br />                    The name of the dimension is included as part of the name of the hierarchy. This is the default value.<br /><br /> **ExcludeDimensionName**:<br />                    The name of the dimension is not included as part of the name of the hierarchy.|  
|**ID**|Contains the unique identifier of the cube dimension.|  
|**MemberUniqueNameStyle**|Determines how unique names are generated for members of hierarchies contained within the cube dimension. This property can have the following values:<br /><br /> **Native**:<br />                      [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] automatically determines the unique names of members. This is the default value.<br /><br /> **NamePath**: [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] generates a compound name consisting of the name of each level and the caption of the member.|  
|**Name**|Contains the friendly name of the cube dimension. By default, the name of a cube dimension is the same as the name of the database dimension, unless another cube dimension of the same name is already defined.|  
|**Visible**|Determines whether the cube dimension is visible. The default value is **True**.|  
  
## See Also  
 [Dimensions &#40;Analysis Services - Multidimensional Data&#41;](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)  
  
  
