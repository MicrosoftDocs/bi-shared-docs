---
title: "Deploy Analysis Services tabular models from Visual Studio | Microsoft Docs"
description: Learn how to deploy a tabular model project from Visual Studio, including deployment properties and options.
ms.date: 04/03/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Deploy a tabular model from Visual Studio

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Deploying a tabular model project from Visual Studio is a simple process, however, certain steps must be taken to ensure your model is deployed to the correct server instance or Power BI workspace and with the right configuration options.  
  
Tabular models are defined with several deployment-specific properties. When you deploy, a connection to the instance specified in the **Server** property is established. A new model with the name specified in the **Database** property is then created on that instance, if one does not already exist. Metadata from the model project's Model.bim file is used to configure objects in the model database on the deployment server. With the **Processing Option**, you can specify whether or not just the model metadata is deployed, creating the model database, or if **Default** or **Full** is specified, impersonation credentials used to connect to data sources are passed in-memory from the model workspace database to the deployed model database. Analysis Services then runs processing to populate data into the deployed model. Once the deployment and processing is complete, the model can then be connected to by client reporting applications like Power BI and Excel.  

::: moniker range="asallproducts-allversions || power-bi-premium-current"

Deploying a tabular model project from Visual Studio to a **Power BI Premium** workspace has a few extra steps to complete processing on the first deployment. To learn more, see [Deploy model projects from Visual Studio to Power BI](/power-bi/service-premium-connect-tools#deploy-model-projects-from-visual-studio-ssdt).

::: moniker-end
  
## Deployment properties  

 The project deployment options and deployment server properties specify how and where a model is deployed to a staging or production Analysis Services environment. While default property settings are defined for all model projects, depending on your particular deployment requirements, you can change these property settings for each project.
  
### Deployment Options
  
|Property|Default setting|Description|  
|--------------|---------------------|-----------------|  
|**Processing Option**|**Default**|Specifies the type of processing required when changes to objects are deployed. This property has the following options:<br /><br /> **Default** - This setting specifies Analysis Services will determine the type of processing required. Unprocessed objects will be processed, and if required, recalculating attribute relationships, attribute hierarchies, user hierarchies, and calculated columns. This setting generally results in a faster deployment time than using the Full processing option.<br /><br /> **Do Not Process** - This setting specifies only the metadata will be deployed. After deploying, it may be necessary to run a process operation on the deployed model to update and recalculate data.<br /><br /> **Full** - This setting specifies that both the metadata is deployed and a process full operation is performed. This assures that the deployed model has the most recent updates to both metadata and data.|  
|**Transactional Deployment**|**False**|Specifies whether or not the deployment is transactional. By default, the deployment of all or changed objects is not transactional with the processing of those deployed objects. Deployment can succeed and persist even though processing fails. You can change this to incorporate deployment and processing in a single transaction.|  
|**ADAL Cache**|**Default**|Specifies use of the USEADALCache connection string property when connecting to Azure Analysis Services.|  
  
### Deployment Server
  
|Property|Default setting|Description|  
|--------------|---------------------|-----------------|  
|**Server**|**localhost**|Specifies the [Azure Analysis Services server resource URL](/azure/analysis-services/analysis-services-connect#get-the-server-name), [Power BI Workspace Connection URL](/power-bi/service-premium-connect-tools#to-get-the-workspace-connection-url), or SQL Server Analysis Services instance name to which the model will be deployed.|  
|**Edition**|The same edition as the instance in which the Workspace database is located.|This property specifies the edition of the Analysis Services server to which the model will be deployed. The server edition defines various features that can be incorporated into the project. By default, the edition will be of the local Analysis Services server, which if you are using an integrated workspace will be the Visual Studio edition.|  
|**Database**|**\<projectname>**|This property specifies the name of the Analysis Services database in which model objects will be instantiated upon deployment. This name will also be specified in a reporting client data connection or an .bism data connection file.<br /><br /> You can change this name at any time when you are authoring the model. If you change the name after you have deployed the model, changes that you have made after deployment will not affect the model that you previously deployed. For example, if you open a solution named **TestDB** and deploy your solution with the default model Database name Model, and then modify the solution and renamed the model Database **Sales**, the instance of Analysis Services the solutions were deployed to will display separate databases, one named Model and one named Sales.|  
|**Model Name**|**Model**|This property specifies the model name as shown in client applications and tools.|
  
## Deploy a tabular model  
  
- In **Solution Explorer**, right-click the project name, and then click **Deploy**.
  
     The **Deploy** dialog box will appear and indicate the status of the metadata deployment and the processing (unless Processing Option property is set to Do Not Process) of each table included in the model. 
  
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

When deployed the first time, a semantic model is created in the workspace by using metadata from the model.bim. As part of the deployment operation, after the model has been created in the workspace from model metadata, processing to load data into the model from data sources **will fail**.

Processing fails because unlike when deploying to an Azure or SQL Server Analysis Server instance, where data source credentials are prompted for as part of the deployment operation, when deploying to a Premium workspace data source credentials cannot be specified as part of the deployment operation. Instead, after metadata deployment has succeeded and the model has been created, data source credentials are then specified in the Power BI Service in semantic model settings. In the workspace, click **Semantic models** > **Settings** > **Data source credentials** > **Edit credentials**.

> [!IMPORTANT]
> During public preview, role memberships cannot be specified in the model project. If your model project fails to deploy, make sure there are no users specified in any roles. After the model has successfully deployed, specify users for model roles in the Power BI service.

::: moniker-end

> [!NOTE]
> For DirectQuery models, if the model contains calculated items, calculated columns, or calculated tables, after being deployed you must perform a **Process Recalc** on the database. To learn more about processing a model database from SSMS, see [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md).

After the deployment process is complete, use SSMS to connect to the server or workspace and verify the new model database object has been created.

## See also

 [Tabular model solution deployment](../../analysis-services/deployment/tabular-model-solution-deployment.md)  
 [Configure default data modeling and deployment properties](../../analysis-services/tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md)  
 [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md)