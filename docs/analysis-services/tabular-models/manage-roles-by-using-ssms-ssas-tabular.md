---
title: "Manage Analysis Services tabular model roles by using SSMS | Microsoft Docs"
description: Learn how to create, edit, and manage roles for a deployed tabular model by using SQL Server Management Studio.
ms.date: 04/12/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Create and manage roles in SSMS

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

This article describes how to use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] (SSMS) to create roles, define role permissions, and add users for deployed tabular models or Power BI Premium datasets. To learn about using Visual Studio to create and manage roles for tabular model projects, see [Create and manage roles in Visual Studio](create-and-manage-roles-ssas-tabular.md).

## Use SSMS

### To create a new role
  
1. In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the tabular model database for which you want to create a new role, then right click on **Roles**, and then click **New Role**.  
  
2. In the **Create Role** dialog box, in the Select a page window, click **General**.  
  
3. In the general settings window, in the **Name** field, type a name for the role.  
  
     Use names that clearly identify the member type, for example, Finance Managers or Human Resources Specialists, and be sure the name doesn't include a comma. By default, the name of the default role will be incrementally numbered for each new role.
  
4. In **Set the database permissions for this role**, select one of the following permissions options:  
  
    |Permission|Description|  
    |----------------|-----------------|  
    |**Full control (Administrator)**|Members can make modifications to the model schema and can view all data.|  
    |**Process database**|Members can run Process and Process All operations. Cannot modify the model schema and cannot view data.|  
    |**Read**|Members are allowed to view data (based on row filters) but cannot make any changes to the model schema.|  
  
5. In the **Create Role** dialog box, in the Select a page window, click **Membership**.  
  
6. In the membership settings window, click **Add**, and then in the **Select Users or Groups** dialog box, add users or groups you want to add as members.  
  
7. If the role you are creating has Read permissions, you can add row filters for any table by using a DAX formula. To add row filters, in the **Role Properties - \<rolename>** dialog box, in **Select a page**, click on **Row Filters**.  
  
8. In the row filters window, select a table, then click on the **DAX Filter** field, and then in the **DAX Filter - \<tablename>** field, type a DAX formula.  
  
    > [!NOTE]  
    >  The DAX Filter - \<tablename> field does not contain an AutoComplete query editor or insert function feature.  
  
9. Click **Ok** to save the role.  
  
### To copy a role  
  
1. In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to copy, then expand **Roles**, then right click on the role, and then click **Duplicate**.  
  
### To edit a role  
  
- In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to edit, then expand **Roles**, then right click on the role, and then click **Properties**.  
  
     In the **Role Properties** \<rolename> dialog box, you can change permissions, add or remove members, and add/edit row filters.  
  
### To delete a role  
  
- In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to delete, then expand **Roles**, then right click on the role, and then click **Delete**.  

## Script

Roles for deployed models and datasets can be scripted by using [Tabular Model Scripting Language (TMSL)](../tmsl/tabular-model-scripting-language-tmsl-reference.md) to create or modify the [Roles object](../tmsl/roles-object-tmsl.md). TMSL scripts can be executed in SSMS or with the [Invoke-ASCmd](/powershell/module/sqlserver/invoke-ascmd?view=sqlserver-ps&preserve-view=true) PowerShell cmdlet.

Right-click the database object > **Script** > **Script database as** > **CREATE or REPLACE To** > **New Query Editor Window**. Roles are defined in the roles object, for example:

```json
        "roles": [
          {
            "name": "Sales Manager",
            "modelPermission": "read"
          },
          {
            "name": "Sales Analyst US",
            "modelPermission": "read",
            "tablePermissions": [
              {
                "name": "DimGeography",
                "filterExpression": "DimGeography[CountryRegionCode] = \"US\" "
              }
            ]
          }
        ],
```

## See also

[Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md)  
