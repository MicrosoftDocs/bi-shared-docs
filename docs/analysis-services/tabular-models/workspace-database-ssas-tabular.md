---
title: "Analysis Services workspace database | Microsoft Docs"
description: Learn that the tabular model workspace database is created when you create a new tabular model project in Visual Studio with Analysis Services projects.
ms.date: 04/20/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Workspace database

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

The tabular model workspace database, used during model authoring, is created when you create a new tabular model project in Visual Studio with Analysis Services projects.
  
## Specifying a workspace instance  

  When you create a new tabular model project, you specify an Analysis Services server instance to use while authoring your project:

**Integrated workspace** - Recommended. Utilizes Visual Studio's own internal instance. Use this setting when creating a project that will be deployed to Azure Analysis Services.

**Workspace server** - A workspace database is created on an explicit instance,  often on the same computer as Visual Studio or another computer in the same network. While you can specify an Azure Analysis Services server, it's not recommended. Using a Power BI workspace as the Workspace server is not supported.
  
### Integrated workspace

With Integrated workspace, a working database is created in-memory using Visual Studio's own implicit instance. Integrated workspace mode significantly reduces the complexity of authoring tabular projects because a separate explicit server is not required.

By using Integrated workspace mode, Visual Studio dynamically starts its own internal instance in the background and loads the database. You can add and view tables, columns, and data in the model designer. If you add additional tables, columns, relationships, etc., you're modifying the workspace database. Integrated workspace mode does not change how Visual Studio works with a workspace server and database. What changes is where Visual Studio hosts the workspace database.

You can select Integrated workspace mode when creating a new tabular model project.

![SSAS Integrated Workspace Mode](../../analysis-services/tabular-models/media/ssas-integrated-workspace-mode.png)

By using the Workspace Database and Workspace Server properties for model.bim, you can discover the name of the temporary database and the TCP port of the internal instance where Visual Studio hosts the database. You can connect to the workspace database with SQL Server Management Studio (SSMS) as long as Visual Studio has the database loaded. The Workspace Retention setting specifies that Visual Studio keeps the workspace database on disk, but no longer in memory after a model project is closed. This ensures less memory is consumed than if the model was kept in memory at all times. If you want to control these settings, set the Integrated Workspace Mode property to False and then provide an explicit workspace server. An explicit workspace server also make senses if the data you are importing into a model exceeds the memory capacity of your Visual Studio workstation.

> [!NOTE]  
>When using Integrated workspace mode, the local Analysis Services instance is 64-bit, while Visual Studio runs in the 32-bit environment of Visual Studio. If you're connecting to special data sources, make sure you install both the 32-bit and 64-bit versions of the corresponding data providers on your workstation. The 64-bit provider is required for the 64-bit Analysis Services instance and the 32-bit version is required for the Table Import Wizard in Visual Studio.

### Workspace server

 A workspace database is created on the instance, specified in the Workspace Server property, when you create a new project by using one of the tabular model project templates in Visual Studio. Each tabular model project will have its own workspace database. You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to view the workspace database on the server. The workspace database name includes the project name, followed by an underscore, followed by the username, followed by an underscore, followed by a GUID.  
  
 The workspace database resides in-memory while the tabular model project is open in Visual Studio. When you close the project, the workspace database is either kept in-memory, stored to disk and removed from memory (default), or removed from memory and not stored on disk, as determined by the Workspace Retention property. For more information about the Workspace Retention property, see Workspace Database Properties later in this article.  
  
 After you've added data to your model project by using the Table Import Wizard or by using copy/paste, when you view the tables, columns, and data in the model designer, you are viewing the workspace database. If you add additional tables, columns, relationships, etc. you are changing the workspace database.  
  
 When you deploy a tabular model project, the deployed model database, which is essentially a copy of the workspace database, is created on the Analysis Services server instance specified in the Deployment Server property. For more information about the Deployment Server property, see [Project properties](../../analysis-services/tabular-models/project-properties-ssas-tabular.md).  
  
 The model workspace database typically resides on localhost or a local named instance of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server. You can use a remote instance to host the workspace database, however, this configuration is not recommended due to latency during data queries and other restrictions. Optimally, the instance of that will host the workspace databases is on the same computer as Visual Studio. Authoring model projects on the same computer as the instance that hosts the workspace database can improve performance.  
  
 Remote workspace databases have the following restrictions:  
  
- Potential latency during queries.  
  
- The Data Backup property cannot be set to **Backup to disk**.  
  
- You cannot import data from a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] workbook when creating a new tabular model project by using the Import from [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] project template.  
  
> [!IMPORTANT]  
> The model's compatibility level and the workspace server must correspond.  

> [!NOTE]  
> If any of the tables in your model will contain a large number of rows, consider importing only a subset of the data during model authoring. By importing a subset of the data, you can reduce processing time and consumption of workspace database server resources.

> [!NOTE]  
> The preview window in the Select Tables and Views page in the Table Import Wizard, Edit Table Properties dialog box, and Partition Manager dialog box show tables, columns, and rows at the data source, and may not show the same tables, columns, and rows as the workspace database.  

## Workspace database properties  

 Workspace database properties are included in the model properties. To view model properties, in Visual Studio, in **Solution Explorer**, click the **Model.bim** file. Model properties can be configured using the **Properties** window. Workspace database specific properties include:  
  
> [!NOTE]  
> **Integrated Workspace Mode**, **Workspace Server**, **Workspace Retention**, and **Data Backup** properties have default settings applied when you create a new model project. You can change the default settings for new model projects on the **Data Modeling** page in **Analysis Server** settings in the Tools\Options dialog box. These properties, as well as others, can also be set for each model project in the **Properties** window. Changing default settings will not apply to model projects already created. For more information, see [Configure default data modeling and deployment properties](../../analysis-services/tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md).  
  
|Property|Default Setting|Description|  
|--------------|---------------------|-----------------|  
|**Integrated Workspace Mode**|True, False|If Integrated workspace mode is selected for the workspace database when the project is created, this property will be True. If **Workspace server** mode is selected when the project is created, this property will be False. | 
|**Workspace database**|Name|The name of the workspace database. This property cannot be edited when **Integrated Workspace Mode** is **True**.|  
|**Workspace Retention**|Unload from memory|Specifies how a workspace database is retained after a model project is closed. A workspace database includes model metadata and imported data. In some cases, the workspace database can be very large and consume a large amount of memory. By default, when you close a model project in Visual Studio, the workspace database is unloaded from memory. When changing this setting it is important to consider your available memory resources as well as how often you plan to work on the model project. This property setting has the following options:<br /><br /> **Keep in memory** - Specifies to keep the workspace database in memory after a model project is closed. This option will consume more memory; however, when opening a model project in Visual Studio, fewer resources are consumed and the workspace database will load faster.<br /><br /> **Unload from memory** - Specifies to keep the workspace database on disk, but no longer in memory after a model project is closed. This option will consume less memory; however, when opening a model project in Visual Studio, the workspace database must be re-attached; additional resources are consumed and the model project will load more slowly than if the workspace database is kept in memory. Use this option when in-memory resources are limited or when working on a remote workspace database.<br /><br /> **Delete workspace** - Specifies to delete the workspace database from memory and not keep the workspace database on disk after the model project is closed. This option will consume less memory and storage space; however, when opening a model project in Visual Studio, additional resources are consumed and the model project will load more slowly than if the workspace database is kept in memory or on-disk. Use this option when only occasionally working on model projects.<br /><br /> The default setting for this property can be changed on the **Data Modeling** page in **Analysis Server** settings in the Tools\Options dialog box. This property cannot be edited when **Integrated Workspace Mode** is **True**.|  
|**Workspace Server**|localhost|This property specifies the default server that will be used to host the workspace database while the model project is being authored in Visual Studio. All available instances running on the local computer are included in the listbox.<br /><br /> To specify a different server (running in Tabular mode), type the server name. The user logged on must be an Administrator on the server.<br /><br /> Note that It is recommended you specify a local server as the workspace server. For workspace databases on a remote server, importing from [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] is not supported, data cannot be backed up locally, and the user interface may experience latency during queries.<br /><br /> The default setting for this property can be changed on the Data Modeling page in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] settings in the Tools\Options dialog box. This property cannot be edited when **Integrated Workspace Mode** is **True**.|  
  
## Using SSMS to manage the workspace database

 You can use SSMS to connect to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that hosts a workspace database. Typically, there is no management of the workspace database necessary; the exception, is to detach or delete a workspace database. Do not use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to manage the workspace database while the project is open in the model designer. Doing so could lead to data loss.

## See also  

[Model properties](../../analysis-services/tabular-models/model-properties-ssas-tabular.md)
