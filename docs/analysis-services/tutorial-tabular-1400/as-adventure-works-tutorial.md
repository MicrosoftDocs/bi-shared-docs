---
title: "Analysis Services Adventure Works Internet Sales tutorial (1500) | Microsoft Docs"
ms.date: 02/20/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: tutorial
ms.author: owend
ms.reviewer: owend
author: minewiskan
---
# Adventure Works Internet Sales tutorial (1500)

[!INCLUDE[ssas-appliesto-sql2019-later-aas](../../includes/ssas-appliesto-sql2019-later-aas.md)]

This tutorial provides lessons on how to create and deploy a tabular model at the [1500 compatibility level](../tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md). If you're new to Analysis Services and tabular modeling, completing this tutorial is the quickest way to learn how to create and deploy a basic tabular model by using Visual Studio with Analysis Services projects. Once you have the prerequisites in-place, it should take two to three hours to complete.  

If you intend to deploy to SQL Server Analysis Services 2017 server, you can still complete this tutorial. Select the 1400 compatibility level when creating a new project in Lesson 1. 
  
## What you learn   
  
-   How to create a new tabular model project at the **1500 compatibility level** in Visual Studio.
  
-   How to import data from a relational database into a tabular model project workspace database.  
  
-   How to create and manage relationships between tables in the model.  
  
-   How to create calculated columns, measures, and Key Performance Indicators that help users analyze critical business metrics.  
  
-   How to create and manage perspectives and hierarchies that help users more easily browse model data by providing business and application-specific viewpoints.  
  
-   How to create partitions that divide table data into smaller logical parts that can be processed independent from other partitions.  
  
-   How to secure model objects and data by creating roles with user members.  
  
-   How to deploy a tabular model to an **Azure Analysis Services** server or **SQL Server Analysis Services** by using Visual Studio.  
  
## Prerequisites  

To complete this tutorial, you need:  

-   An Azure subscription. If you don't already have a subscription, create a [free account](https://azure.microsoft.com/free/).

-   An [Azure Synapse Analytics](https://docs.microsoft.com/azure/sql-data-warehouse/create-data-warehouse-portal) (SQL Data Warehouse) named **AdventureWorksDW** with the **sample AdventureWorksDW database**.

-   An Azure Analysis Services server (recommended).  See [create a server](https://docs.microsoft.com/azure/analysis-services/analysis-services-create-server). Or, SQL Server 2019 Analysis Services server in Tabular mode. Download a free [SQL Server 2019 Developer Edition](https://www.microsoft.com/sql-server/sql-server-downloads).

-   The latest version of [Visual Studio](https://visualstudio.microsoft.com/downloads/). Any edition, including the free Community edition work.

-   The latest [Microsoft Analysis Services Projects](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects) (VSIX) package installed in Visual Studio. 

-   The latest version of [SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms).    

-   A client application such as [Power BI Desktop](https://powerbi.microsoft.com/desktop/) or Excel. 

## Scenario  

This tutorial is based on Adventure Works Cycles, a fictitious company. Adventure Works is a large, multinational manufacturing company that produces and distributes bicycles, parts, and accessories for commercial markets in North America, Europe, and Asia. The company employs 500 workers. Additionally, Adventure Works employs several regional sales teams throughout its market base. Your project is to create a tabular model for sales and marketing users to analyze Internet sales data in the AdventureWorksDW database.  
  
To complete the tutorial, you must complete various lessons. In each lesson, there are tasks. Completing each task in order is necessary for completing the lesson. While in a particular lesson there may be several tasks that accomplish a similar outcome, but how you complete each task is slightly different. This method shows there is often more than one way to complete a task, and to challenge you by using skills you've learned in previous lessons and tasks.  
  
The purpose of the lessons is to guide you through authoring a basic tabular model by using many of the features included in Visual Studio with Analysis Services projects. Because each lesson builds upon the previous lesson, you should complete the lessons in order.

## Lessons  

This tutorial includes the following lessons:  
  
|Lesson|Estimated time to complete|  
|----------|------------------------------|  
|[1 - Create a new tabular model project](../tutorial-tabular-1400/as-lesson-1-create-a-new-tabular-model-project.md)|10 minutes|  
|[2 - Get data](../tutorial-tabular-1400/as-lesson-2-get-data.md)|10 minutes|  
|[3 - Mark as Date Table](../tutorial-tabular-1400/as-lesson-3-mark-as-date-table.md)|3 minutes|  
|[4 - Create relationships](../tutorial-tabular-1400/as-lesson-4-create-relationships.md)|10 minutes|  
|[5 - Create calculated columns](../tutorial-tabular-1400/as-lesson-5-create-calculated-columns.md)|15 minutes|
|[6 - Create measures](../tutorial-tabular-1400/as-lesson-6-create-measures.md)|30 minutes|  
|[7 - Create Key Performance Indicators (KPI)](../tutorial-tabular-1400/as-lesson-7-create-key-performance-indicators.md)|15 minutes|  
|[8 - Create perspectives](../tutorial-tabular-1400/as-lesson-8-create-perspectives.md)|5 minutes|  
|[9 - Create hierarchies](../tutorial-tabular-1400/as-lesson-9-create-hierarchies.md)|20 minutes|  
|[10 - Create partitions](../tutorial-tabular-1400/as-lesson-10-create-partitions.md)|15 minutes|  
|[11 - Create roles](../tutorial-tabular-1400/as-lesson-11-create-roles.md)|15 minutes|  
|[12 - Analyze in Excel](../tutorial-tabular-1400/as-lesson-12-analyze-in-excel.md)|5 minutes| 
|[13 - Deploy](../tutorial-tabular-1400/as-lesson-13-deploy.md)|5 minutes|  
  
## Supplemental lessons  

These lessons are not required to complete the tutorial, but can be helpful in better understanding advanced tabular model authoring features.  
  
|Lesson|Estimated time to complete|  
|----------|------------------------------|  
|[Detail Rows](../tutorial-tabular-1400/as-supplemental-lesson-detail-rows.md)|10 minutes|
|[Dynamic security](../tutorial-tabular-1400/as-supplemental-lesson-dynamic-security.md)|30 minutes|
|[Ragged hierarchies](../tutorial-tabular-1400/as-supplemental-lesson-ragged-hierarchies.md)|20 minutes| 

  
## Next steps  

To get started, see [Lesson 1: Create a new tabular model project](../tutorial-tabular-1400/as-lesson-1-create-a-new-tabular-model-project.md).  
  
  
  

