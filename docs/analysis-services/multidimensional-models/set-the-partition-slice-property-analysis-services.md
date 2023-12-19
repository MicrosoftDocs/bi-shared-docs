---
title: "Set the Partition Slice Property (Analysis Services) | Microsoft Docs"
description: Set the Slice property to improve query performance by overriding default slices generated for MOLAP and HOLAP partitions.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Set the Partition Slice Property (Analysis Services)
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  A data slice is an important optimization feature that helps direct queries to the data of the appropriate partitions. Explicitly setting the Slice property can improve query performance by overriding default slices generated for MOLAP and HOLAP partitions. Additionally, the Slice property provides an extra validation check when processing the partition.  
  
 You can specify a data slice after you create a partition, but before processing it, using the Slice property. On the Partitions tab, expand a measure group, right-click a partition, and select **Properties**.  
  
 For an explanation of data slice benefits, see [Set the Slice on your SSAS Cube Partition](https://go.microsoft.com/fwlink/?LinkId=317783).  
  
## Defining a Slice  
 Valid values for a slice property are an MDX member, set, or tuple. The following examples illustrate valid slice syntax:  
  
|Slice|Member, set or tuple|  
|-----------|--------------------------|  
|[Date].[Calendar].[Calendar Year].&[2010]|Specify this slice on a partition containing facts from year 2010 (assuming the model includes a Date dimension with Calendar Year hierarchy, where 2010 is a member). Although the partition source WHERE clause or table might already filter by 2010, specifying the Slice provides an additional check during processing, as well as more targeted scans during query execution.|  
|{ [Sales Territory].[Sales Territory Country].&[Australia], [Sales Territory].[Sales Territory Country].&[Canada] }|Specify this slice on a partition containing facts that include sales territory information. A slice can be an MDX set consisting of two or more members.|  
|[Measures].[Sales Amount Quota] > '5000'|This slice shows an MDX expression.|  
  
 A data slice of a partition should reflect, as closely as possible, the data in the partition. For example, if a partition is limited to 2012 data, the partition's data slice should specify the 2012 member of the Time dimension. It is not always possible to specify a data slice that reflects the exact contents of a partition. For example, if a partition contains data for only January and February, but the levels of the Time dimension are Year, Quarter, and Month, the Partition Wizard cannot select both the January and February members. In such cases, select the parent of the members that reflect the partition's contents. In this example, select Quarter 1.  
  
> [!NOTE]  
>  Note that dynamic MDX functions (such as [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) or [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) are not supported in the Slice property for partitions. You must define the slice by using explicit tuples or member references.  
>   
>  For example, rather than using the range operator (:) to define a range, you would need to enumerate each member by the specific years.  
>   
>  If you need to define a complex slice, we recommend that you define the tuples in the slice by using an XMLA Alter script. Then, you can use either the ascmd command-line tool or the [Analysis Services Execute DDL Task](/sql/integration-services/control-flow/analysis-services-execute-ddl-task) in Integration Services to run the script and create the specified set of members immediately before you process the partition.  
>   
>  Slicer cannot be defined on a dimension that has a Many-To-Many relationship or unmaterialized referenced relationship with the partition measure group. The slicer validation fails with error "The slice specified for the ... attribute is incorrect". This is because an unmaterialized relationship has no valid dimension attribute data ID range data for evaluation of slicer validation.   

## See Also  
 [Create and Manage a Local Partition &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/create-and-manage-a-local-partition-analysis-services.md)  
  
  
