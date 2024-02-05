---
title: "Write-Enabled Dimensions | Microsoft Docs"
description: Learn how write-enabled dimensions give business users the ability to update members.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: olap
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Write-Enabled Dimensions
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../includes/ssnotedepnextavoid-md.md)]  
  
 The data in a dimension is generally read-only. However, for certain scenarios, you may want to write-enable a dimension. In [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], write-enabling a dimension enables business users to modify the contents of the dimension and see the immediate effect of changes on the hierarchies of the dimension. Any dimension that is based on a single table can be write-enabled. In a write-enabled dimension, business users and administrators can change, move, add, and delete attribute members within the dimension. These updates are referred to collectively as *dimension writeback*.  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] supports dimension writeback on all dimension attributes and any member of a dimension may be modified. For a write-enabled cube or partition, updates are stored in a writeback table separate from the cube's source tables. However, for a write-enabled dimension, updates are recorded directly in the dimension's table. Also, if the write-enabled dimension is included in a cube with multiple partitions where some or all their data sources have copies of the dimension table, only the original dimension table is updated during a writeback process.  
  
 Write-enabled dimensions and write-enabled cubes have different but complementary features. A write-enabled dimension gives business users the ability to update members, whereas a write-enabled cube gives them the ability to update cell values. Although these two features are complementary, you do not have to use both features in combination. A dimension does not have to be included in a cube for dimension writeback to occur. A write-enabled dimension can also be included in a cube that is not write-enabled. You use different procedures to write-enable dimensions and cubes, and to maintain their security.  
  
 The following restrictions apply to dimension writeback:  
  
-   When you create a new member, you must include every attribute in a dimension. You cannot insert a member without specifying a value for the key attribute of the dimension. Therefore, creating members is subject to any constraints (such as non-null key values) that are defined on the dimension table.  
  
-   Dimension writeback is supported only for star schemas. In other words, a dimension must be based on a single dimension table directly related to a fact table. After you write-enable a dimension, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] validates this requirement when you deploy to an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database or when you build an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.  
  
 Any existing member of a writeback dimension can be modified or deleted. When a member is deleted, the deletion cascades to all child members. For example, in a Customer dimension that contains CountryRegion, Province, City, and Customer attributes, deleting a country/region would delete all provinces, cities, and customers that belong to the deleted country/region. If a country/region has only one province, deleting that province would delete the country/region also.  
  
 Members of a writeback dimension can only be moved within the same level. For example, a city could be moved to the City level in a different country/region or province, but a city cannot be moved to the Province or CountryRegion level. In a parent-child hierarchy, all members are leaf members, and therefore a member may be moved to any level other than the **(All)** level.  
  
 If a member of a parent-child hierarchy is deleted, the member's children are moved to the member's parent. Update permissions on the relational table are required on the deleted member, but no permissions are required on the moved members. When an application moves a member in a parent-child hierarchy, the application can specify in the UPDATE operation whether descendents of the member are moved with the member or are moved to the member's parent. To recursively delete a member in a parent-child hierarchy, a user must have update permissions on the relational table for the member and all the member's descendants.  
  
> [!NOTE]  
>  Updates to the parent attribute in a parent-child hierarchy must not include updates to any other properties or attributes.  
  
 All changes to a dimension cause the dimension structure to be modified. Each change to a dimension is considered a single transaction, requiring incremental processing to update the dimension structure. Write-enabled dimensions have the same processing requirements as any other dimension.  
  
> [!NOTE]  
>  Dimension writeback is not supported by linked dimensions.  
  
## Security  
 The only business users who can update a write-enabled dimension are those in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database roles that have been granted read/write permission to the dimension. For each role, you can control which members can and cannot be updated. For business users to update write-enabled dimensions, their client application must support this capability. For such users, a write-enabled dimension must be included in a cube that was processed since the dimension last changed. For more information, see [Authorizing access to objects and operations &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/authorizing-access-to-objects-and-operations-analysis-services.md).  
  
 Users and groups included in the Administrators role can update the attribute members of a write-enabled dimension, even if the dimension is not included in a cube.  
  
## See Also  
 [Database Dimension Properties](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/database-dimension-properties.md)   
 [Write-Enabled Partitions](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-write-enabled-partitions.md)   
 [Dimensions &#40;Analysis Services - Multidimensional Data&#41;](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)  
  
  
