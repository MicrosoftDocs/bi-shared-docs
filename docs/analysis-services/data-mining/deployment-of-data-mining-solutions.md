---
title: "Deployment of Data Mining Solutions | Microsoft Docs"
description: Learn how to deploy your data mining models to a production environment in SQL Server Analysis Services so that users can perform tasks.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Deployment of Data Mining Solutions
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  The last step in the data mining process is to deploy the models to a production environment. Deployment is important because it makes the models available to users so that you can perform any of the following tasks:  
  
-   Use the models to create predictions and make business decisions. For information about the tools you can use to create queries, see [Data Mining Query Tools](../../analysis-services/data-mining/data-mining-query-tools.md).  
  
-   Embed data mining functionality directly into an application. You can include Analysis Management Objects (AMO) or an assembly that contains a set of objects that your application can use to create, alter, process, and delete mining structures and mining models.  
  
-   Create reports that let users request predictions, view trends, or compare models.  
  
 This section provides detailed information about deployment options.  
  
 [Requirements for Deployment of Data Mining Solutions](#bkmk_Reqs)  
  
 [Deploying a Relational Solution](#bkmk_RelationalSltn)  
  
 [Deploying a Multidimensional Solution](#bkmk_MDSltn)  
  
 [Related Resources](#bkmk_Resources)  
  
## In This Section  
 [Deploy a Data Mining Solution to Previous Versions of SQL Server](../../analysis-services/data-mining/deploy-a-data-mining-solution-to-previous-versions-of-sql-server.md)  
  
 [Export and Import Data Mining Objects](../../analysis-services/data-mining/export-and-import-data-mining-objects.md)  
  
##  <a name="bkmk_Reqs"></a> Requirements for Deployment of Data Mining Solutions  
 The instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] data.  
  
 Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.  
  
 When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.  
  
###  <a name="bkmk_RelationalSltn"></a> Deploying a Relational Solution  
 When you deploy a relational data mining solution, the required data mining objects are created within a new [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, and the objects are processed by default. You can change processing options by using the configuration property, **Processing Option**. For more information, see [Configure Analysis Services Project Properties &#40;SSDT&#41;](../../analysis-services/multidimensional-models/configure-analysis-services-project-properties-ssdt.md).  
  
 By default, only incremental changes are deployed each time. In other words, you can modify a mining model, and when you re-deploy the project, only that mining model would be updated. However, if you have multiple clients editing the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, this can lead to errors. To change the default deployment mode so that the entire database is refreshed when you deploy the solution, change the **Deployment Mode** property  
  
 In a relational data mining solution, the only objects that must be deployed are the data source definition, any data source views that were used, the mining structures, and all dependent mining models.  
  
###  <a name="bkmk_MDSltn"></a> Deploying a Multidimensional Solution  
 When you deploy a multidimensional data mining solution, this solution creates your data mining objects within the same database as the source cube.  
  
 When you process the mining structure or mining model, you must process the source cube as well. For this reason, deploying a solution that uses OLAP mining models can take longer than relational data mining solutions.  
  
 Typically data mining objects also use the same data sources and data source views that are used for the cube. However, you can add data sources and data source views that are targeted specifically to data mining. For example, typically a cube would not contain data about prospective clients, or external data not used in the multidimensional objects.  
  
##  <a name="bkmk_Resources"></a> Related Resources  
 [Moving Data Mining Objects](../../analysis-services/data-mining/moving-data-mining-objects.md)  
  
 If your model is based on relational data only, exporting and importing objects using DMX is the easiest way to move models.  
  
 [Move an Analysis Services Database](../../analysis-services/multidimensional-models/move-an-analysis-services-database.md)  
  
 When models use a cube as a data source, refer to this topic for more information about how to move models and their supporting cube data.  
  
 [Deploy Analysis Services Projects &#40;SSDT&#41;](../../analysis-services/multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
 Provides general information about deployment of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projects, and describes the properties that you can set as part of the project configuration.  
  
## See Also  
 [Processing a multidimensional model &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services.md)   
 [Data Mining Query Tools](../../analysis-services/data-mining/data-mining-query-tools.md)   
 [Processing Requirements and Considerations &#40;Data Mining&#41;](../../analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
