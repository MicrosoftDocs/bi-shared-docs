---
title: "Create and manage roles for Analysis Services tabular models projects | Microsoft Docs"
description: Learn how to create and manage roles during model authoring by using the Role Manager dialog box in SQL Server Data Tools.
ms.date: 04/12/2022
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Create and manage roles in Visual Studio

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

This article describes how to use Role Manager in Visual Studio to create roles, define role permissions, and add users for a tabular model project. To learn about creating and managing roles for a deployed model, see [Create and manage roles in SSMS](manage-roles-by-using-ssms-ssas-tabular.md).

> [!NOTE]
> Model roles in Power BI are used only for row-level security filters (RLS). Only Read permission are supported. Use the Power BI security model to control permissions beyond RLS.

## Use Role Manager
  
To create, edit, copy, and delete roles, use the **Role Manager** dialog box. To view the **Role Manager** dialog box, in Visual Studio, click **Extensions** > **Model** > **Role Manager**.  

### To create a role
  
1. In **Role Manager**, click **New**.  
  
     A new highlighted role is added to the Roles list.  
  
1. In the **Roles** list, in the **Name** field, type a name for the role.  
  
     Use names that clearly identify the member type, for example, Finance Managers or Human Resources Specialists, and be sure the name doesn't include a comma. By default, the name of the default role will be incrementally numbered for each new role.
  
1. In the **Permissions** field, click the down arrow and then select one of the following permission types:  
  
    |Permission|Description|  
    |----------------|-----------------|  
    |**None**|Members cannot make any modifications to the model schema and cannot query data.|  
    |**Read**|Members are allowed to query data (based on row filters) but cannot make any changes to the model schema.|  
    |**Read and Process**|Members are allowed to query data (based on row-level filters) and run Process and Process All operations, but cannot make any changes to the model schema.|  
    |**Process**|Members can run Process and Process All operations. Cannot modify the model schema and cannot query data.|  
    |**Administrator**|Members can make modifications to the model schema and can query all data.|  
  
1. To enter a description for the role, click the **Description** field, and then type a description.  
  
1. If the role you are creating has Read or Read and Process permission, you can add row filters by using a DAX formula. To add row filters, click the **Row Filters** tab, then select a table, then click the **DAX Filter** field, and then type a DAX formula.  
  
1. To add members to the role, click the **Members** tab, and then click **Add**.  
  
    > [!NOTE]  
    >  Role members can also be added to a deployed model by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]. For more information, see [Manage Roles by using SSMS](../../analysis-services/tabular-models/manage-roles-by-using-ssms-ssas-tabular.md).  
  
1. In the **Select Users or Groups** dialog box, enter Windows user or Windows group objects as members.  
  
1. Click **Ok**.  
  
## See also

 [Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md)   
 [Perspectives](../../analysis-services/tabular-models/perspectives-ssas-tabular.md)   
 [CUSTOMDATA Function (DAX)](/dax/customdata-function-dax)  
