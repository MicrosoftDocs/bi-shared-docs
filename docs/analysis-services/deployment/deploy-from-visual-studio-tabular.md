---
title: "Deploy Analysis Services tabular models from Visual Studio | Microsoft Docs"
ms.date: 04/03/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Deploy a tabular model From Visual Studio

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

Use the tasks in this article to deploy a tabular model solution by using the Deploy command in Visual Studio with Analysis Services projects. Before you deploy your tabular model solution, you must first specify the Deployment Options and Deployment Server properties. For more information about deployment properties and settings, see [Tabular model solution deployment](../../analysis-services/deployment/tabular-model-solution-deployment.md).  

## Deploy a tabular model  
  
- In **Solution Explorer**, right-click the project name, and then click **Deploy**.
  
     The **Deploy** dialog box will appear and indicate the status of the metadata deployment and the processing (unless Processing Option property is set to Do Not Process) of each table included in the model. After the deployment process is complete, use SSMS to connect to the Analysis Services instance and verify the new model database object has been created or use a client reporting application to connect to the deployed model.  
  
## Deploy Status

 The **Deploy** dialog box enables you to monitor the progress of a Deploy operation. A deploy operation can also be stopped.  
  
 **Status**  
 Indicates whether the Deploy operation was successful or not.  
  
 **Details**  
 Lists the metadata items that were deployed, the status for each metadata item, and provides a message of any issues.  
  
 **Stop Deploy**  
 Click to halt the Deploy operation. This option is useful if the Deploy operation is taking too long, or if there are too many errors.  

::: moniker range="asallproducts-allversions || power-bi-premium-current"

### Deploying to a Power BI Premium workspace

When deployed the first time, a dataset is created in the workspace by using metadata from the model.bim. As part of the deployment operation, after the dataset has been created in the workspace from model metadata, processing to load data into the dataset from data sources **will fail**.

Processing fails because unlike when deploying to an Azure or SQL Server Analysis Server instance, where data source credentials are prompted for as part of the deployment operation, when deploying to a Premium workspace data source credentials cannot be specified as part of the deployment operation. Instead, after metadata deployment has succeeded and the dataset has been created, data source credentials are then specified in the Power BI Service in dataset settings. In the workspace, click **Datasets** > **Settings** > **Data source credentials** > **Edit credentials**.

> [!IMPORTANT]
> During public preview, role memberships cannot be specified in the model project. If your model project fails to deploy, make sure there are no users specified in any roles. After the model has successfully deployed, specify users for dataset roles in the Power BI service.

::: moniker-end

> [!NOTE]
> For DirectQuery models, if the model contains calculated items, calculated columns, or calculated tables, after being deployed you must perform a **Process Recalc** on the database. To learn more about processing a model database from SSMS, see [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md).

## See also

 [Tabular model solution deployment](../../analysis-services/deployment/tabular-model-solution-deployment.md)  
 [Configure default data modeling and deployment properties](../../analysis-services/tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md)  
 [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md)