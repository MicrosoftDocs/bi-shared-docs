---
title: "Configure Analysis Services tabular model roles | Microsoft Docs"
description: Learn how to configure roles in tabular models so you can define member permissions for a model.
ms.date: 02/10/2022
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Roles

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Roles in tabular models define member permissions for a model. Members of the role can perform actions on the model as defined by the role permission. Roles defined with read permissions can also provide additional security at the row-level by using row-level filters.
  
For Azure Analysis Services and Power BI semantic models, users must be in your Microsoft Entra ID and usernames and groups specified must be by organizational email address or UPN. For SQL Server Analysis Services, roles contain user members by Windows username or by Windows group, and permissions (read, process, administrator).

> [!IMPORTANT]  
> When using Visual Studio to create roles and add organizational users to a tabular model project that will be deployed to Azure Analysis Services or Power BI, use [Integrated workspace](workspace-database-ssas-tabular.md).

> [!IMPORTANT]  
> For users to connect to a deployed model by using a reporting client application, you must create at least one role with at least Read permission to which those users are members.  
  
Information in this article is meant for tabular model authors who define roles by using the Role Manager dialog box in SSDT. Roles defined during model authoring apply to the model workspace database. After a model database has been deployed, model database administrators can manage (add, edit, delete) role members by using SSMS.
  
## Understanding roles

Roles are used in Analysis Services to manage model data access. There are two types of roles:  
  
- The server role, a fixed role that provides administrator access to an Analysis Services server instance. Server roles do not apply to Power BI. Instead, Power BI uses [workspace roles](/power-bi/collaborate-share/service-roles-new-workspaces).
  
- Database roles, roles defined by model authors and administrators to control access to a model database and data for non-administrator users.
  
Roles defined for a tabular model are database roles. That is, the roles contain members consisting of users or groups that have specific permissions that define the action those members can take on the model database. A role is created as a separate object in the database, and applies only to the database in which that role is created. Users and groups are included in the role by the model author, which by default has Administrator permissions on the workspace database server; for a deployed model, by an administrator.  
  
Roles in tabular models can be further defined with row filters, also known as *row-level-security*. Row filters use DAX expressions to define the rows in a table, and any related rows in the many direction, that a user can query. Row filters using DAX expressions can only be defined for the Read and Read and Process permissions. In Power BI, model roles are defined in Power BI Desktop and apply only to row-level security. To learn more, see [Row filters](#row-filters) later in this article.

By default, when you create a new tabular model project, the project does not have any roles. Roles can be defined by using the Role Manager dialog box in SSDT. When roles are defined during model authoring, they are applied to the model workspace database. When the model is deployed, the same roles are applied to the deployed model. After a model has been deployed, members of the server role ([Analysis Services Administrator) and database administrators can manage the roles associated with the model and the members associated with each role by using SSMS.  

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

## Permissions

Role permissions described in this section apply only to Azure Analysis Services and SQL Server Analysis Services. In Power BI, permissions are defined for the semantic model. To learn more, see [Manage semantic model access](/power-bi/connect-data/service-datasets-manage-access-permissions).

Each role has a single defined database permission (except for the combined Read and Process permission). By default, a new role will have the None permission. That is, once members are added to the role with the None permission, they cannot modify the database, run a process operation, query data, or see the database unless a different permission is granted.  
  
A group or user can be a member of any number of roles, each role with a different permission. When a user is a member of multiple roles, the permissions defined for each role are cumulative. For example, if a user is a member of a role with the Read permission, and also a member of a role with None permission, that user will have Read permissions.  
  
Each role can have one the following permissions defined:  
  
|Permissions|Description|Row filters using DAX|  
|-----------------|-----------------|----------------------------|  
|None|Members cannot make any modifications to the model database schema and cannot query data.|Row filters do not apply. No data is visible to users in this role|  
|Read|Members are allowed to query data (based on row filters) but cannot see the model database in SSMS, cannot make any changes to the model database schema, and the user cannot process the model.|Row filters can be applied. Only data specified in the row filter DAX formula is visible to users.|  
|Read and Process|Members are allowed to query data (based on row-level filters) and run process operations by running a script or package that contains a process command, but cannot make any changes to the database. Cannot view the model database in SSMS.|Row filters can be applied. Only data specified in the row filter DAX formula can be queried.|  
|Process|Members can run process operations by running a script or package that contains a process command. Cannot modify the model database schema. Cannot query data. Cannot query the model database in SSMS.|Row filters do not apply. No data can be queried in this role|  
|Administrator|Members can make modifications to the model schema and can query all data in the model designer, reporting client, and SSMS.|Row filters do not apply. All data can be queried in this role.|  

> [!NOTE]
> Members with Read and Read and Process permissions can query data based on row filters but cannot see the model database in SSMS. Members cannot make changes to the model database schema and cannot process the model. However, in SQL Server Analysis Services 2019 and earlier, members can use [DMVs](../instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services.md?preserve-view=true) to determine measure definitions. SQL Server Analysis Services 2022 and later block access to DMVs for improved security.

::: moniker-end

## Row filters

Row filters, commonly known as [row-level security in Power BI](/power-bi/admin/service-admin-rls), define which rows in a table can be queried by members of a particular role. Row filters are defined for each table in a model by using DAX formulas.  
  
Row filters can be defined only for roles with Read and Read and Process permissions. By default, if a row filter is not defined for a particular table, members of a role that has Read or Read and Process permission can query all rows in the table unless cross-filtering applies from another table.  
  
Once a row filter is defined for a particular table, a DAX formula, which must evaluate to a TRUE/FALSE value, defines the rows that can be queried by members of that particular role. Rows not included in the DAX formula will cannot be queried. For example, for members of the Sales role, the Customers table with the following row filters expression, *=Customers [Country] = "USA"*, members of the Sales role, will only be able to see customers in the USA.  
  
Row filters apply to the specified rows as well as related rows. When a table has multiple relationships, filters apply security for the relationship that is active. Row filters will be intersected with other row filers defined for related tables, for example:  
  
|Table|DAX expression|  
|-----------|--------------------|  
|Region|=Region[Country]="USA"|  
|ProductCategory|=ProductCategory[Name]="Bicycles"|  
|Transactions|=Transactions[Year]=2020|  
  
The net effect of these permissions on the Transactions table is that members will be allowed to query rows of data where the customer is in the USA, and the product category is bicycles, and the year is 2020. Users would not be able to query any transactions outside of the USA, or any transactions that are not bicycles, or any transactions not in 2020 unless they are a member of another role that grants these permissions.  
  
You can use the filter, *=FALSE()*, to deny access to all rows for an entire table.  

To learn more about model roles in Power BI, see [row-level security in Power BI](/power-bi/admin/service-admin-rls). 

### Dynamic security

Dynamic security provides a way to define row-level security based on the user name of the user currently logged on or the CustomData property returned from a connection string. In order to implement dynamic security, you must include in your model a table with login (Windows user name) values for users as well as a field that can be used to define a particular permission; for example, a dimEmployees table with a login ID (domain\username) as well as a department value for each employee.  
  
To implement dynamic security, you can use the following functions as part of a DAX formula to return the user name of the user currently logged on, or the CustomData property in a connection string:  
  
|Function|Description|  
|--------------|-----------------|  
|[USERNAME Function (DAX)](/dax/customdata-function-dax)|Returns the domain\ username of the user currently logged on.|  
|[CUSTOMDATA Function (DAX)](/dax/customdata-function-dax)|Returns the CustomData property in a connection string.|  
  
You can use the LOOKUPVALUE function to return values for a column in which the Windows user name is the same as the user name returned by the USERNAME function or a string returned by the CustomData function. Queries can then be restricted where the values returned by LOOKUPVALUE match values in the same or related table.  
  
For example, using this formula:  
  
`='dimDepartment'[DepartmentId]=LOOKUPVALUE('dimEmployees'[DepartmentId], 'dimEmployees'[LoginId], USERNAME(), 'dimEmployees'[LoginId], 'dimDepartment'[DepartmentId])`  
  
The LOOKUPVALUE function returns values for the dimEmployees[DepartmentId] column where the dimEmployees[LoginId] is the same as the LoginID of the user currently logged on, returned by USERNAME, and values for dimEmployees[DepartmentId] are the same as values for dimDepartment[DepartmentId]. The values in DepartmentId returned by LOOKUPVALUE are then used to restrict the rows queried in the dimDepartment table, and any tables related by DepartmentId. Only rows where DepartmentId are also in the values for the DepartmentId returned by LOOKUPVALUE function are returned.  
  
**dimEmployees**
  
|LastName|FirstName|LoginId|DepartmentName|DepartmentId|  
|--------------|---------------|-------------|--------------------|------------------|  
|Brown|Kevin|Adventure-works\kevin0|Marketing|7|  
|Bradley|David|Adventure-works\david0|Marketing|7|  
|Dobney|JoLynn|Adventure-works\JoLynn0|Production|4|  
|Baretto DeMattos|Paula|Adventure-works\Paula0|Human Resources|2|  
  
 **dimDepartment**
  
|DepartmentId|DepartmentName|  
|------------------|--------------------|  
|1|Corporate|  
|2|Executive General and Administration|  
|3|Inventory Management|  
|4|Manufacturing|  
|5|Quality Assurance|  
|6|Research and Development|  
|7|Sales and Marketing|  
  
## Testing roles

When authoring a model project in Visual Studio, you can use the Analyze in Excel feature to test the efficacy of the roles you have defined. From the **Model** menu in the model designer, when you click **Analyze in Excel**, before Excel opens, the **Choose Credentials and Perspective** dialog box appears. In this dialog, you can specify the current username, a different username, a role, and a perspective with which you will use to connect to the workspace model as a data source. To learn more, see [Analyze in Excel](./tabular-model-designer-ssas.md).  
  
## Scripting roles

Roles for deployed models and semantic models can be scripted by using [Tabular Model Scripting Language (TMSL)](../tmsl/tabular-model-scripting-language-tmsl-reference.md) to create or modify the [Roles object](../tmsl/roles-object-tmsl.md). TMSL scripts can be executed in SSMS or with the [Invoke-ASCmd](/powershell/module/sqlserver/invoke-ascmd?view=sqlserver-ps&preserve-view=true) PowerShell cmdlet.
  
## See also

[Create and Manage Roles](../../analysis-services/tabular-models/create-and-manage-roles-ssas-tabular.md)  
 [Perspectives](../../analysis-services/tabular-models/perspectives-ssas-tabular.md)   
 [Analyze in Excel](./tabular-model-designer-ssas.md)   
 [USERNAME Function (DAX)](/dax/username-function-dax)   
 [LOOKUPVALUE Function (DAX)](/dax/lookupvalue-function-dax)   
 [CUSTOMDATA Function (DAX)](/dax/customdata-function-dax)  
  
