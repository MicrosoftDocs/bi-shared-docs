---
title: "Set Impersonation Options (SSAS - Multidimensional) | Microsoft Docs"
description: Learn how to set impersonation options in the Impersonation Information dialog box when configuring a data source object.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Set Impersonation Options (SSAS - Multidimensional)
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  When creating a **data source** object in an Analysis Services model, one of the settings that you must configure is an impersonation option. This option determines whether Analysis Services assumes the identity of a specific Windows user account when performing local operations related to the connection, such as loading an OLE DB data provider or resolving user profile information in environments that support roaming profiles.  
  
 For connections that use Windows authentication, the impersonation option also determines the user identity under which queries execute on the external data source. For example, if you set the impersonation option to **contoso\dbuser**, queries used to retrieve data during processing will execute as **contoso\dbuser** on the database server.  
  
 This topic explains how to set impersonation options in the **Impersonation Information** dialog box when configuring a data source object.  
  
## Set impersonation options in SQL Server Data Tools  
  
1.  Double-click a data source in Solution Explorer to open Data Source Designer.  
  
2.  Click the **Impersonation Information** tab in Data Source Designer.  
  
3.  Choose an option described in [Impersonation options](#bkmk_options) in this topic.  
  
## Set impersonation options in Management Studio  
 In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], open the **Impersonation Information** dialog box by clicking the ellipsis (**...**) button for the following properties of these dialog boxes:  
  
-   **Database Properties** dialog box, through the Data Source Impersonation Info property.  
  
-   **Data Source Properties** dialog box, through the Impersonation Info property.  
  
-   **Assembly Properties** dialog box, through the Impersonation Info property.  
  
##  <a name="bkmk_options"></a> Impersonation options  
 All options are available in the dialog box, but not all options are appropriate for every scenario. Use the following information to determine the best option for your scenario.  
  
 **Use a specific user name and password**  
 Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of a Windows user account specified in this format: *\<Domain name>***\\***\<User account name>*.  
  
 Choose this option to use a dedicated, least-privilege Windows user identity that you have created specifically for data access purposes. For example, if you routinely create a general purpose account for retrieving data used in reports, you can specify that account here.  
  
 For multidimensional databases, the specified credentials will be used for processing, ROLAP queries, out-of-line bindings, local cubes, mining models, remote partitions, linked objects, and synchronization from target to source.  
  
 For DMX OPENQUERY statements, this option is ignored and the credentials of the current user will be used rather than the specified user account.  
  
 **Use the service account**  
 Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the object. This is the default option. In previous releases, this was the only option you could use. You might prefer this option to monitor data access at the service level rather than individual user accounts.  
  
 In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], depending on the operating system you are using, the service account might be NetworkService or a built-in virtual account created for a specific [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance. If you choose the service account for a connection that uses Windows authentication, remember to create a database login for this account and grant read permissions, as it will be used to retrieve data during processing. For more information about the service account, see [Configure Windows Service Accounts and Permissions](/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions).  
  
> [!NOTE]  
>  When using database authentication, you should choose the **Use the service account** impersonation option if the service is running under the dedicated virtual account for Analysis Services. This account will have permissions to access local files. If the service runs as NetworkService, a better alternative is to use a least privilege Windows user account that has **Allow log on locally** permissions. Depending on the account you provide, you might also need to grant file access permissions on the Analysis Services program folder.  
  
 For multidimensional databases, the service account credentials will be used for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.  
  
 For DMX OPENQUERY statements, local cubes, and mining models, the credentials of the current user will be used even if you choose the service account option. The service account option is not supported for out-of-line bindings.  
  
> [!NOTE]  
>  Errors can occur when processing a data mining model from a cube if the service account does not have administrator permissions on the Analysis Services instance. For more information, see [Mining Structure: Issue while Processing when DataSource is OLAP Cube](https://go.microsoft.com/fwlink/?LinkId=251610).  
  
 **Use the credentials of the current user**  
 Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of the current user for out-of-line bindings, DMX OPENQUERY, local cubes, and mining models.  
  
 With the exception of local cubes and processing using out-of-line bindings, this option is not supported for multidimensional databases.  
  
 **Default** or **Inherit**  
 The dialog box uses **Default** for the impersonation options set at the database level and **Inherit** for impersonation options set at the data source level.  
  
 **Data Sources - Inherit Option**  
  
 At the data source level, **Inherit** specifies that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] should use the impersonation option of the parent object. In a multidimensional model, the parent object is the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database. Choosing the **Inherit** option lets you centrally manage the impersonation settings for this and other data sources that are part of the same database. For this option to be meaningful, choose a specific Windows user name and password at the database level. Otherwise, the combination of **Inherit** on the data source and **Default** on the database are equivalent to using service account option.  
  
 To specify a Windows user name and password at the database level, do the following:  
  
1.  Right-click the database in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and select **Properties**.  
  
2.  In **Data Source Impersonation Info**, specify a Windows user name and password.  
  
3.  Right-click each data source and view its properties to ensure that each one is using the **Inherit** option.  
  
 For more information about default settings at the database level, see [Set Multidimensional Database Properties &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/set-multidimensional-database-properties-analysis-services.md).  
  
 **Databases - Default option**  

 For multidimensional databases, **Default** means use the service account, and current user for data mining operations.  
  
## See Also  
 [Create a Data Source &#40;SSAS Multidimensional&#41;](../../analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional.md)   
 [Set Data Source Properties &#40;SSAS Multidimensional&#41;](../../analysis-services/multidimensional-models/set-data-source-properties-ssas-multidimensional.md)   

  
  
