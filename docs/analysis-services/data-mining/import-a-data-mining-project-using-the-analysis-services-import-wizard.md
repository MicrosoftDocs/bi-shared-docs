---
title: "Import a Data Mining Project using the Import Analysis Services Database Wizard | Microsoft Docs"
description: Learn how to import the metadata of an existing data mining project to create a new data mining project in SQL Server Data Tools.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: how-to

---
# Import a data mining project by using the Import Analysis Services Database Wizard
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  This article describes how to create a new data mining project by importing the metadata from an existing data mining project on another server. Use the template **Import from Server (Multidimensional and Data Mining) Project** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].
  
## Import data sources, mining structures, and mining models from an existing data mining project  
 When you use the template **Import from Server (Multidimensional and Data Mining) Project**, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates a new data mining project and then copies the metadata from the specified data mining project. The new project contains the same data sources, data source views, mining structures, and mining models as the database you imported from. However, you can't use the project until you update certain properties and process the objects as described in this article.  
  
-   The import process doesn't copy the data itself from the source server to the new data mining project. The process imports only the definitions of the data sources and data source views. After the import process completes and creates the objects, you must populate the objects with data by training the mining structures and dependent models. You can use the command **Process All** in Data Mining Designer to train the models and structures.  
  
-   If you're importing a project that you created in a previous version of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], the data source might use providers that aren't installed on the server you're importing the project to. If you encounter errors when processing the imported mining structures, right-click each data source and select **Open Designer** to edit the connection string and review the provider properties.  
  
     At this time, you might also need to verify that the account you're using to process the data mining objects or query data mining models has the necessary permissions on the data source.  
  
-   By default, when you import a project, the workspace database is set to localhost, or whatever default instance is configured as the **Default Target Server** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]. To set this property, from the **Options** menu, select **Business Intelligence Designers**, select **Analysis Services**, and then select **General**.  
  
     In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], you can set another, separate option to configure the default deployment server for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] tabular model projects. The setting, **Default Deployment Server**, determines the default workspace database for tabular model projects. You can't use instances that support tabular models for data mining projects.  
  
     If you can't change the default deployment database to use an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] running in multidimensional or data mining mode, you can always specify the deployment database by using the **Project Properties** dialog box.  
  
### To create a new data mining project by importing an existing data mining project  
  
1.  In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **File** menu, select **New** and then select **Project**.  
  
1.  In the **New Project** dialog box, under **Installed Templates**, select **Business Intelligence** > **Analysis Services** and then select **Import from Server (Multidimensional/Data Mining)**.  

  
1.  For **Name**, type a name for the project, specify a location and solution name, and then select **OK**.  

  
     The **Import Analysis Services Database wizard** starts. Select **OK** on the Welcome page to proceed.  
  
1.  On the **Select Source Database** page, for **Server**, specify the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that contains the solution you want to import.  

  
     For **Database**, choose the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that contains the data mining objects you want to import, and then select **Next**.  
  
    > [!IMPORTANT]  
    >  You can't specify the objects you want to import. When you choose an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the wizard imports all multidimensional and data mining objects.  
  
1.  The **Completing the Wizard** page displays the progress of the import operation. You can't cancel the operation or change the objects being imported. Select **Finish** when done.  

  
     The new project automatically opens in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].
  
## See also  
 [Project Properties](../../analysis-services/tabular-models/project-properties-ssas-tabular.md)  
  
  
