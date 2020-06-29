---
title: "Perspectives in Analysis Services tabular models | Microsoft Docs"
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
# Perspectives in tabular models

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

Perspectives, in tabular models, define viewable subsets of a model that provide focused, business-specific, or application-specific viewpoints of the model.  

Tabular models can be very complex for users to explore. A single model can represent the contents of a complete data warehouse with many tables, measures, and dimensions. Such complexity can be daunting to users who may only need to interact with a small part of the model in order to satisfy their business intelligence and reporting requirements.  
  
In a perspective, tables, columns, and measures (including KPIs) are defined as field objects. You can select the viewable fields for each perspective. For example, a single model may contain product, sales, financial, employee, and geographic data. While a sales department requires product, sales, promotions, and geography data, they likely do not require employee and financial data. Similarly, a human resources department does not require data about sales promotions and geography.  
  
When a user connects to a model (as a data source) with defined perspectives, the user can select the perspective they want to use. For example, when connecting to a model data source in Excel, users in Human Resources can select the Human Resources perspective on the Select Tables and Views page of the Data Connection Wizard. Only fields (tables, columns, and measures) defined for the Human Resources perspective will be visible in the PivotTable Field List.  
  
Perspectives are not meant to be used as a security mechanism, but as a tool for providing a better user experience. All security for a particular perspective is inherited from the underlying model. Perspectives cannot provide access to model objects to which a user does not already have access. Security for the model database must be resolved before access to objects in the model can be provided through a perspective. Security roles can be used to secure model metadata and data. For more information, see [Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md).  

## Create and manage perspectives
  
To create, edit, delete, copy, and view perspectives for a model project, use the **Perspectives** dialog box. In Visual Studio, click **Extensions** > **Model** > **Perspectives**.  
  
### To add a perspective  
  
- To add a new perspective, click **New Perspective**. You can then check and uncheck field objects to be included and provide a name for the new perspective.  
  
     If you create an empty perspective with all of the field object fields, then a user using this perspective will see an empty Field List. Perspectives should contain at least one table and column.  
  
### To edit a perspective  
  
- To modify a perspective, check and uncheck fields in the perspective's column, which adds and removes field objects from the perspective.  
  
### To rename a perspective  
  
- When you hover over a perspective's column header (the name of the perspective), the **Rename** button appears. To rename the perspective, click **Rename**, and then enter a new name or edit the existing name.  
  
### To delete a perspective  
  
- When you hover over a perspective's column header (the name of the perspective), the **Delete** button appears. To delete the perspective, click the **Delete** button, and then click **Yes** in the confirmation window.  
  
### To copy a perspective  
  
- When you hover over a perspective's column header, the **Copy** button appears. To create a copy of that perspective, click the **Copy** button. A copy of the selected perspective is added as a new perspective to the right of existing perspectives. The new perspective inherits the name of the copied perspective and a *- Copy* annotation is appended to the end of the name. For example, if a copy of the *Sales* perspective is created, the new perspective is called *Sales - Copy*.  
  
## Testing perspectives

When authoring a model, you can use the Analyze in Excel feature in the model designer to test the efficacy of the perspectives you have defined. From the **Model** menu in the model designer, when you click **Analyze in Excel**, before Excel opens, the **Choose Credentials and Perspective** dialog box appears. In this dialog, you can specify the current username, a different user, a role, and a perspective with which you will use to connect to the model workspace database as a data source and view data.  

## See also

[Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md)   
[Hierarchies](../../analysis-services/tabular-models/hierarchies-ssas-tabular.md)  
