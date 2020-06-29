---
title: "Bi-directional cross filters in Analysis Services tabular models| Microsoft Docs"
ms.date: 01/29/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Bi-directional cross filters in tabular models

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

  Bi-directional cross filters in tabular models eliminates the need for hand-crafted DAX workarounds for propagating filter context across table relationships.  
  
 Breaking the concept down into its component parts: *cross filtering* is the ability to set a filter context on a table based on values in a related table, and *bi-directional* is the transference of a filter context to second related table on the other side of a table relationship. As the name implies, you can slice in both directions of the relationship rather than just one way.  Internally, two-way filtering expands filter context to query a superset of your data.  
  
 ![SSAS-BIDI-1-Filteroption](../../analysis-services/tabular-models/media/ssas-bidi-1-filteroption.PNG "SSAS-BIDI-1-Filteroption")  
  
 There are two types of cross filters: One-way and two-way filtering. One-way is the traditional many-to-one filter direction between fact and dimensional tables in that relationship. Two-way is a cross-filter that enables the filter context of one relationship to be used as the filter context for another table relationship, with  one table common to both relationships.  
  
 Given **DimDate** and **DimProduct** with foreign key relationships to **FactOnlineSales**, a two-way cross filter is equivalent of **FactOnlineSales-to-DimDate** plus **FactOnlineSales-to-DimProduct** used simultaneously.  
  
 Bi-directional cross filters can be an easy  fix to the many-to-many query design problem that has challenged tabular and Power Pivot developers in the past. If you've used the DAX workaround for many-to-many relationships in tabular or Power Pivot models, you can try applying a two-way filter to see if it produces expected results.  
  
 When creating a bi-directional cross filter, keep the following points in mind:  
  
-   Think before you enable two-way filters.  
  
     If you enable two-way filters everywhere, your data could be over-filtered in ways that you might not expect.  You might also inadvertently introduce ambiguity by creating more than one potential query path. To avoid both issues, plan on using a  combination of one-way and two-way filters.  
  
-   Do incremental testing to verify the impact of each filter change on your model.The Analyze in Excel feature in Visual Studio works well for incremental testing. As a best practice, periodically follow that up with tests using other reporting clients so that there are no surprises later.  
  
> [!NOTE]  
>  Tabular model designer in Visual Studio includes a default that determines whether bi-directional cross filters are attempted automatically. If you enable bi-directional filters by default, it will enable two-way filtering only if the model clearly articulates one query path through a chain of table relationships.  
  
## Set the default  

 Single directional filters are the default. You can change the default for all new projects created in the designer, or on the model itself when the project already exists.  
  
 At the project level, the setting is evaluated when you create the project so if you change the default to bi-directional, you'll see the effects of your selection when you create the next project.  
  
1.  In Visual Studio, select **Tools** > **Options** > **Analysis Services Tabular Designers** > **New project settings**.  
  
2.  Set **Default filter direction** to either **Single direction** or **Both directions**.  
  
 Alternatively, you can change the default on the model.  
  
1.  In Solution Explorer, select **Model.bim** > **Properties** ,  
  
2.  Set **Default filter direction** to either **Single direction** or **Both directions**.  
  
## Keep in mind  

 Understanding when and how a bi-directional cross filter can be a matter of trial and error to see how it works in your scenario. At times, you'll find that the built-in behaviors are not sufficient and will need to fall back on DAX computations to get the job done. In the **See Also** section, you'll find several links to additional resources on this subject.  
  
 In practical terms, cross-filtering can enable forms of data exploration typically delivered only through a many-to-many construction. Having said that, it's important to recognize that bi-directional cross-filtering is not a many-to-many construct.  An actual many-to-many table configuration remains unsupported in the designer for tabular models in this release.  
  
## See also  

 [Create and manage relationships in Power BI Desktop](https://support.powerbi.com/knowledgebase/articles/464155-create-and-manage-relationships-in-power-bi-desktop)   
 [A practical example of how to handle simple many-to-manay relationships in Power Pivot and tabular models](https://social.technet.microsoft.com/wiki/contents/articles/22202.a-practical-example-of-how-to-handle-simple-many-to-many-relationships-in-power-pivotssas-tabular-models.aspx)   
 [Resolving many-to-many relationships leveraging DAX cross-table filtering](https://blog.gbrueckl.at/2012/05/resolving-many-to-many-relationships-leveraging-dax-cross-table-filtering/)   
 [Many to many revolution (SQLBI blog)](https://www.sqlbi.com/articles/many2many/)  
  
  
