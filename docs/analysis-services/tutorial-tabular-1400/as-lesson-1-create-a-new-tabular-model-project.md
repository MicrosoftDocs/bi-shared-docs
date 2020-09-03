---
title: "Analysis Services tutorial lesson 1: Create a new tabular model project | Microsoft Docs"
ms.date: 02/20/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: tutorial
ms.author: owend
ms.reviewer: owend
author: minewiskan
---
# Create a tabular model project

[!INCLUDE[ssas-appliesto-sql2019-later-aas-pbip](../includes/ssas-appliesto-sql2019-later-aas-pbip.md)]

In this lesson, you use Visual Studio with Microsoft Analysis Services projects to create a new tabular model project. Once your new project is created, you can begin adding data and authoring your model. This lesson also gives you a brief introduction to the tabular model authoring environment in Visual Studio.  
  
Estimated time to complete this lesson: **10 minutes**  
  
## Prerequisites

This article is the first lesson in a tabular model authoring tutorial. To complete this lesson, there are several prerequisites you need to have in-place. To learn more, see [Analysis Services - Adventure Works tutorial](../tutorial-tabular-1400/as-adventure-works-tutorial.md).  
  
## Create a new tabular model project  
  
#### To create a new tabular model project  
  
1.  In Visual Studio, in **Get started**, click **Create a new project**.  
  
2.  In **Create a new project**, search for and then select **Analysis Services Tabular Project**.  
  
3.  In  **Configure your new project**, in **Project name**, type **AW Internet Sales**. Specify a location for the project files. Leave **Framework** the default. 
  
    By default, **Solution Name** is the same as the project name; however, you can type a different solution name.  
  
4.  Click **Create**.  
  
5.  In the **Tabular model designer** dialog box, select **Integrated workspace**.  
  
    The workspace hosts a tabular model database with the same name as the project during model authoring. Integrated workspace means Visual Studio uses a built-in instance, eliminating the need to install a separate Analysis Services server instance just for model authoring. To learn more, see [Workspace database](../tabular-models/workspace-database-ssas-tabular.md).
      
6.  In **Compatibility level**, select **SQL Server 2019 / Azure Analysis Services (1500)**, and then click **OK**.   
 
    ![Screenshot of the Tabular model designer dialog box with the Integrated workspace option and Compatibility level drop-down list called out.](../tutorial-tabular-1400/media/as-lesson1-tmd.png)
      
When complete, your new tabular model project will open in Visual Studio.

## Understanding the tabular model authoring environment  

Now that you've created a new tabular model project, let's take a moment to explore the tabular model authoring environment in Visual Studio.  
  
After your project is created, it opens in Visual Studio. On the right side, in **Tabular Model Explorer**, you see a tree view of the objects in your model. Since you haven't yet imported data, the folders are empty. You can right-click an object folder to perform actions, similar to the menu bar. As you step through this tutorial, you use the Tabular Model Explorer to navigate different objects in your model project.

![Screenshot of the Tabular Model Explorer dialog box.](../tutorial-tabular-1400/media/as-lesson1-tme.png)

Click the **Solution Explorer** tab. Here, you see your **Model.bim** file. If you don't see the designer window to the left (the empty window with the Model.bim tab), in **Solution Explorer**, under **AW Internet Sales Project**, double-click the **Model.bim** file. The Model.bim file contains the metadata for your model project. 

![Screenshot of the Solution Explorer section with the Model.bim file highlighted.](../tutorial-tabular-1400/media/as-lesson1-se.png)
  
Click **Model.bim**. In the **Properties** window, you see the model properties, most important of which is the **DirectQuery Mode** property. This property specifies if the model is deployed in In-Memory mode (Off) or DirectQuery mode (On). For this tutorial, you author and deploy your model in In-Memory mode.

![Screenshot of the Properties window with the Compatibility Level option highlighted and its SQL Server 2019 / Azure Analysis Services (1500) setting called out.](../tutorial-tabular-1400/media/as-lesson1-properties.png)
  
When you create a model project, certain model properties are set automatically according to the Data Modeling settings that can be specified in the **Tools** menu > **Options** dialog box. Data Backup, Workspace Retention, and Workspace Server properties specify how and where the workspace database (your model authoring database) is backed up, retained in-memory, and built. You can change these settings later if necessary, but for now, leave these properties as they are.  

In **Solution Explorer**, right-click **AW Internet Sales** (project), and then click **Properties**. The **AW Internet Sales Property Pages** dialog box appears. You set some of these properties later when you deploy your model.  
  
When you installed the Analysis Services projects extension, several new menu items were added to the Visual Studio environment. Click the **Extensions** menu. From here, you can import data, refresh workspace data, browse your model in Excel, create perspectives and roles, select the model view, and set calculation options. Click the **Table** menu. From here, you can create and manage relationships, specify date table settings, create partitions, and edit table properties. If you click the **Column** menu, you can add and delete columns in a table, freeze columns, and specify sort order. The extension also adds some buttons to the bar. Most useful is the AutoSum feature to create a standard aggregation measure for a selected column. Other toolbar buttons provide quick access to frequently used features and commands.  
  
Explore some of the dialogs and locations for various features specific to authoring tabular models. While some items are not yet active, you can get a good idea of the tabular model authoring environment.  
  
## Next step

[Lesson 2: Get data](../tutorial-tabular-1400/as-lesson-2-get-data.md)