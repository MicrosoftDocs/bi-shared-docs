---
title: "Deploy Analysis Services tabular models from Visual Studio | Microsoft Docs"
ms.date: 01/22/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Deploy a tabular model From Visual Studio (SSDT)

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

  Use the tasks in this article to deploy a tabular model solution by using the Deploy command in Visual Studio.  
  
##  <a name="bkmk_deploy"></a> Configure deployment options and deployment server properties

 Before you deploy your tabular model solution, you must first specify the Deployment Options and Deployment Server properties. For more information about deployment properties and settings, see [Tabular model solution deployment](../../analysis-services/deployment/tabular-model-solution-deployment-ssas-tabular.md).  
  
#### To configure options and properties
  
1.  In **Solution Explorer**, right-click the project name, and then click **Properties**.  
  
2.  In the **\<project name> Properties** dialog, in **Deployment Options**, specify property settings if different from the default settings.  
  
    > [!NOTE]  
    >  For models in cached mode, **Query Mode** is always **In-Memory**.  
  
    > [!NOTE]  
    >  You cannot specify **Impersonation Settings** for models in DirectQuery mode.  
  
3.  In **Deployment Server**, specify the **Server** (name), **Edition**, **Database** (name), and **Cube Name** property settings, if different from the default settings, and then click **OK**.  
  
> [!NOTE]  
>  You can also specify the Default Deployment Server property setting so any new projects you create will automatically be deployed to the specified server. For more information, see [Configure default data modeling and deployment properties](../../analysis-services/tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md).  
  
##  <a name="bkmk_deploy_proc"></a> Deploy a tabular model  
  
#### To deploy a tabular model
  
-   In Visual Studio, on the **Build** menu, click **Deploy \<project name>**.  
  
     The **Deploy** dialog box will appear and indicate the status of the metadata deployment and the processing (unless Processing Option property is set to Do Not Process) of each table included in the model. After the deployment process is complete, use SSMS to connect to the Analysis Services instance and verify the new model database object has been created or use a client reporting application to connect to the deployed model.  
  
##  <a name="bkmk_deploy_status"></a> Deploy Status

 The **Deploy** dialog box enables you to monitor the progress of a Deploy operation. A deploy operation can also be stopped.  
  
 **Status**  
 Indicates whether the Deploy operation was successful or not.  
  
 **Details**  
 Lists the metadata items that were deployed, the status for each metadata item, and provides a message of any issues.  
  
 **Stop Deploy**  
 Click to halt the Deploy operation. This option is useful if the Deploy operation is taking too long, or if there are too many errors.  
 

> [!NOTE]
> For DirectQuery models, if the model contains calculated items, calculated columns, or calculated tables, after being deployed you must perform a **Process Recalc** on the database. To learn more about processing a model database from SSMS, see [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md).

## See also

 [Tabular model solution deployment](../../analysis-services/deployment/tabular-model-solution-deployment-ssas-tabular.md)   
 [Configure default data modeling and deployment properties](../../analysis-services/tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md)   
 [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md)   