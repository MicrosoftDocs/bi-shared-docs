---
title: "Dimension Storage (Analysis Services) | Microsoft Docs"
description: "Learn how dimensions in Microsoft SQL Server Analysis Services support two storage modes: Relational OLAP (ROLAP) and Multidimensional OLAP (MOLAP)."
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: olap
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Dimensions - Storage
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  Dimensions in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] support two storage modes:  
  
-   Relational OLAP (ROLAP)  
  
-   Multidimensional OLAP (MOLAP)  
  
 The storage mode determines the location and form of a dimension's data. MOLAP is the default storage mode for dimensions. **Related topics:**[Partition Storage Modes and Processing](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)  
  
## MOLAP  
 Data for a dimension that uses MOLAP is stored in a multidimensional structure in the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. This multidimensional structure is created and populated when the dimension is processed. MOLAP dimensions provide better query performance than ROLAP dimensions.  
  
## ROLAP  
 Data for a dimension that uses ROLAP is actually stored in the tables used to define the dimension. The ROLAP storage mode can be used to support large dimensions without duplicating large amounts of data, but at the expense of query performance. Because the dimension relies directly on the tables in the data source view used to define the dimension, the ROLAP storage mode also supports real-time OLAP.  
  
> [!IMPORTANT]  
>  If a dimension uses the ROLAP storage mode and the dimension is included in a cube that uses MOLAP storage, any schema changes to its source table must be followed by immediate processing of the cube. Failure to do this may result in inconsistent results when querying the cube. **Related topic:**[Automate Analysis Services Administrative Tasks with SSIS](../../analysis-services/instances/automate-analysis-services-administrative-tasks-with-ssis.md).  
  
## See Also  
 [Partition Storage Modes and Processing](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)  
  
  
