---
title: "Deploy model solutions by using the Deployment Wizard | Microsoft Docs"
description: Learn how the Analysis Services Deployment Wizard uses JSON output files as input files to create a deployment script.
ms.date: 02/07/2022
ms.service: analysis-services
ms.custom:
ms.topic: conceptual
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Deploy model solutions by using the Deployment Wizard

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

The [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Deployment Wizard uses JSON output files generated from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project as input files. These input files are easily modifiable to customize the deployment of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project. The generated deployment script can then either be immediately run or saved for later deployment.  

The Deployment Wizard/Utility is installed with [SQL Server Management Studio](/sql/ssms/download-sql-server-management-studio-ssms) (SSMS). Be sure you're using the latest version. If running from the command prompt, by default, the latest version of  the deployment wizard is installed to C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE.
  
You can deploy by using the wizard as described here. You can also automate deployment or use the Synchronize capability. If the deployed database is large, consider using partitions on target systems. You can automate partition creation and population by using Tabular Object Model (TOM), Tabular Model Scriting Language (TMSL), and Analysis Management Objects (AMO).  
  
> [!IMPORTANT]  
> Neither the output files nor the deployment script will contain the user id or password if these are specified in either the connection string for a data source or for impersonation purposes. Since these are required for processing purposes in this scenario, you will add this information manually. If the deployment will not include processing, you can add this connection and impersonation information as needed after deployment. If the deployment will include processing, you can either add this information within the wizard or in the deployment script after it is saved.  
  
## Run the Deployment Wizard

The Deployment Wizard can be run the following ways:  
  
- **Interactively** - When run interactively, the Deployment Wizard generates a deployment script based on the input files, as modified interactively by user input. The wizard applies any user modifications only to the deployment script. The wizard does not modify the input files.
  
- **From the command prompt** - When run at the command prompt, the Deployment Wizard generates a deployment script based upon the switches that you use to run the wizard. The wizard may any one of the following: prompt you for user input and modify input files based on that input; run a silent, unattended deployment using the input files as is; or create a deployment script that you can use later.  
  
### Run interactively

 When run interactively, the Deployment Wizard reads the values from the input files and presents this information to you. You can modify these input values-such as deployment destination, configuration settings, deployment options, and connection string passwords-or leave them as is. If you change any input values, the wizard uses these changes when generating the deployment script. However, the wizard does not make any changes to the values in the input file.  
  
> [!NOTE]  
> If you want to have the Deployment Wizard modify the input values, run the wizard at the command prompt and set the wizard to run in answer file mode.  
  
 After you review the input values and make any wanted changes, the wizard generates the deployment script. You can run this deployment script immediately on the destination server or save the script for later use.  
  
#### To run the Analysis Services Deployment Wizard interactively
  
- Click **Start**, then type **Analysis Services Deployment Wizard**.  
  
     -or-  
  
- In the **Projects** folder of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, double-click the \<project name>.asdatabase file.

    > [!NOTE]  
    >  If you cannot find the .asdatabase file, try using Search and specify *.asdatabase. Or, you may need to build the project in SSDT.  
  
### Run at the command prompt

 The Deployment Wizard can also be run at the command prompt. When run at the command prompt, you provide the full path to the .asdatabase file and  run the wizard in one of the following modes:  
  
 **Answer file mode**  
 In answer file mode, the wizard lets you interactively modify the input files that were originally generated when the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project was built in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]. The wizard saves these modified input files before generating the deployment script. The modified input files become the new starting point the next time that the wizard is run.  
  
 To run the wizard in answer file mode, use the **/a** switch.  
  
 **Silent mode**  
 In silent mode, the wizard runs a silent, unattended deployment based on the information resident in the input files.  
  
 To run the wizard in silent mode, use the **/s** switch. When you run the wizard in silent mode, messages are output to the console or to a log file if one is provided.  
  
 **Output mode**  
 In output mode, the wizard generates a deployment script for later execution based on the input files.  
  
 To run the wizard in output mode, use the **/o** switch and provide an output file name.  
  
 For more information about these command line switches, see [Deploy model solutions with the Deployment Utility](../../analysis-services/deployment/deploy-model-solutions-with-the-deployment-utility.md).  
  
#### To run the Analysis Services Deployment Wizard at the command prompt
  
1. If installed with SSMS 18.x, open a command prompt and navigate to the default path C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE.
  
2. Type **Microsoft.AnalysisServices.Deployment.exe** followed by the switches that correspond to the mode in which you want to run the wizard.

## Understanding the deployment script

The XMLA deployment script generated by the Deployment Wizard consists of two sections:  
  
- The first part of the deployment script contains the commands required to create, alter, or delete the appropriate [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects in the destination database. By default, the input files generated by the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project are based on an incremental deployment. As a result, the XMLA deployment script will only affect those objects that were changed or deleted.  
  
- The second part of the deployment script contains the commands required to process only the objects created or altered on the destination server (the Process Default option) or to fully process the destination database. You can also choose to have the deployment script contain no processing commands.  
  
 The entire deployment script can execute in a single transaction or in multiple transactions. If the script executes in multiple transactions, the first part of the script executes as a single transaction, and each object is processed in its own transaction.  
  
> [!IMPORTANT]  
> The [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Deployment Wizard only deploys objects into a single [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database. It does not deploy any server level objects or data.  

## Deployment script files - Input used to create deployment script

When you build a project, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] generates files for the project. [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] then puts these files in the Output folder of the project. By default output is put in the \Bin folder. The following table lists the XML files that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates:  
  
|File|Description|  
|---------------|-----------------|  
|\<*project name*>.asdatabase|An XMLA file for Multidimensional or 1100/1103 Tabular model projects, or a JSON file for Tabular 1200 and higher model projects. Contains the declarative definitions for all the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects in the project.|  
|\<*project name*>.deploymenttargets|Contains the name of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance and database in which the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects will be created.|  
|\<*project name*>.configsettings|Contains environment specific settings, such as data source connection information and object storage locations. Settings in this file override settings in the \<*project name*>.asdatabase file.|  
|\<*project name*>.deploymentoptions|Contains deployment options, such as whether deployment is transactional and whether deployed objects should be processed after deployment.|  
  
[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] never stores passwords in the project files.  
  
### Modifying input files

Modifying the values in the input files, or the values retrieved from the input files, makes it possible to change the deployment destination, the configuration settings, and deployment options without editing the whole \<*project name*>.asdatabase file (or a whole script file if you generate a script from an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database). Being able to modify individual files lets you easily create different deployment scripts for different purposes.  

## Deployment script files - Specifying the installation target

The Deployment Wizard reads the installation target information from the \<*project name*>.deploymenttargets file. [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates this file when you build the project. [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] uses the database and server specified on the **Deployment** page of the *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.targets file.  
  
### Modifying the installation target

 In some situations, you may need to deploy a project to a database or instance that is different than the one specified on the **Deployment** page. For example, you may want to deploy the project to a server for testing before deployment, and then deploy it to a production server after testing is finished. You may also want to deploy a completed and tested project to multiple production servers in a Network Load Balancing cluster, or to a staging server and a production server.  
  
 To deploy a project to a different database or instance, change the installation target in the input file by using one of the methods described in the following procedure:  
  
#### To change the installation target after the input files have been generated
  
- Run the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Deployment Wizard interactively. On the **Installation Target** page, specify a new destination for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance and database.  
  
     -or-  
  
- Run the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode. 
  
     -or-  
  
- Modify the \<*project name*>.deploymenttargets file by using any text editor.  

## Deployment script files - Partition and role deployment options

The Deployment Wizard reads the partition and role deployment options from the \<*project name*>.deploymentoptions file. [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates this file when you build the project. [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] then uses the partition and role deployment options of the current project when the \<*project name*>.deploymentoptions file is created.  
  
### Reviewing partition and role deployment options

 The deployment options in the \<*project name*>.deploymentoptions file include the following:  
  
 **Partition deployment options**  
 The \<*project name*>.deploymentoptions file specifies whether existing partitions in the destination database are retained or overwritten (default). If existing partitions are retained, only new partitions will be deployed, and the partitions and aggregation designs on all existing measure groups are left unchanged.  
  
If the measure group in which the partition exists is deleted, the partition is automatically deleted.  
  
 **Role deployment options**  
 The \<*project name*>.deploymentoptions file specifies one of the following role deployment options:  
  
- Existing roles and role members in the destination database are retained, and only new roles and role members are deployed.  
  
- All existing roles and members in the destination database are replaced by the roles and members being deployed.  
  
- Existing roles and role members in the destination database are retained, and no new roles are deployed.  
  
When existing roles and members are retained, the permissions associated with those roles are reset to none. Security permissions are contained by the objects they secure, not by the security roles with which they are associated. For more information about how to work with this behavior by using the Analysis Service Deployment Wizard, see 'Retain Roles and Members' in the Microsoft Knowledge Base.  
  
### Modifying partition and role deployment options

 You may have to deploy the project using different partition and role options than those stored in the \<*project name*>.deploymentoptions file. For example, you may want to retain existing partitions, roles, and role members, instead of replacing all existing partitions, roles, and members as indicated in the \<*project name*>.deploymentoptions file.  
  
 To modify the deployment of partitions and roles in a project, you cannot change the partition and roles settings within the project because the *\<project name>* **Properties Pages** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] does not display these options. If you want to change the deployment options for roles and partitions, you must change this information within the \<*project name*>.deploymentoptions file itself. The following procedure describes how to change the partition and role deployment options within the \<*project name*>.deploymentoptions file.  
  
#### To change the deployment of partitions or roles after the input files have been generated  
  
- Run the Deployment Wizard interactively, and on the **Partition and Role Deployment Options** page, specify new deployment options for the partitions and roles.  
  
     -or-  
  
- Run the Deployment Wizard at the command prompt, and set the wizard to run in answer file mode.
  
     -or-  
  
- Open the \<*project name*>.deploymentoptions in any text editor and manually change the options. The options for PartitionDeployment are DeployPartitions, RetainPartitions. The options for RoleDeployment are DeployRolesAndMembers, DeployRolesRetainMembers, RetainRoles.

## Deployment script files - Solution deployment config settings

The Deployment Wizard reads the partition and role deployment options that you use in the deployment script from the \<*project name*>.configsettings file. For multidimensional projects, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates this file when you build the project. For tabular projects, depending on the version, it may be necessary to run Deployment Wizard in Answer mode to generate the .configsettings file. [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] uses the configuration settings of the current project to create the \<*project name*>.configsettings file.  
  
### Reviewing configuration settings

 The following are the configuration settings stored in the \<*project name*>.configsettings file:  
  
- **Data Source Connection Strings** - These are the connection strings for each data source based on the values specified in the project. The user id and password are always removed from the connection string before the remainder of the string is stored in this file. However, if the Deployment Wizard is deploying directly to an Analysis Services instance, you can add the appropriate user id and password information within the wizard to enable a successful processing of the deployment database. This connection information will not be stored in the deployment script itself if one is saved by the Deployment Wizard.  
  
- **Impersonation Accounts** - This setting specifies the user name that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to run statements in each data source. If no impersonation account is specified, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses its logon account to run statements. If the logon account is granted permissions directly in the data source, all database administrators in all databases in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance have access to the data source through the logon account. If a user account and password is specified, this information is always removed before the impersonation information is stored in this file. However, if the Deployment Wizard is deploying directly to an Analysis Services instance, you can add the appropriate user id and password information within the wizard to enable a successful processing of the deployment database. This impersonation information will not be stored in the deployment script itself if one is saved by the Deployment Wizard.

    > [!NOTE]
    > For tabular models at the 1400 and higher compatibility level with structured provider data source connections, when selecting **Retain configuration settings for existing objects** on the Specify Configuration Properties page of the Wizard, user name and password stored on the target server tabular model database are not retained. Administrators must set the user name and password manually by using SSMS after the deployment completes.
  
- **Key Error Log Files** - This setting specifies the file name and path of the key error log file for each cube, measure group, partition, and dimension in the database.  
  
- **Storage Locations** - This setting specifies the storage location for each cube, measure group, and partition in the database. If no value is provided for an object, the Deployment Wizard uses the default location for the object. For example, partitions use the location for the measure group, measure groups use the location for the cube, and cubes use the default location for objects on the server instance. The storage location can be a local or a Universal Naming Convention (UNC) path.  
  
- **Report Server** - This setting specifies the report server and folder location for each report action defined in each cube in the database.  
  
### Modifying configuration settings

 In some cases, you may need to deploy the project using different configuration settings than those stored in the \<*project name*>.configsettings file. For example, you may want to change the connection string to one or more data sources, or specify storage locations for specific partitions or measure groups.  
  
 To modify the deployment of partitions and roles in a project, you must change this information within the \<*project name*>.configsettings file, as described in the procedure below. You cannot change the partition and roles settings within the project because the *\<project name>* **Properties Pages** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] does not display these options.  
  
> [!NOTE]  
> Configuration settings can apply to all objects or only to newly created objects. Apply configuration settings to newly created objects only when you are deploying additional objects to a previously deployed [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database and do not want to overwrite existing objects. To specify whether configuration settings apply to all objects or only to newly created ones, set this option in the \<*project name*>.deploymentoptions file.  
  
#### To change configuration settings after the input files have been generated  
  
- Run the Deployment Wizard interactively, and on the **Configuration Settings** page, specify the configuration setting for the objects being deployed.  
  
     -or-  
  
- Run the Deployment Wizard at the command prompt and set the wizard to run in answer file mode.
  
     -or-  
  
- Modify the \<*project name*>.configsettings file by using any text editor.  

## Deployment script files - Processing options

The Deployment Wizard reads the processing options from the \<*project name*>.deploymentoptions file. [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates this file when you build the project. [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] uses the processing options specified on the **Deployment** page of *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.deploymentoptions file.  
  
### Reviewing processing options

The configuration settings stored within the \<*project name*>.deploymentoptions file are:  
  
- **Processing Method** - This setting controls whether the deployed objects are processed after deployment and the type of processing that will be performed. There are three processing options:  
  
  - Default processing (default) detects the process state of database objects, and performs processing necessary to deliver unprocessed or partially processed objects to a fully processed state.
  
  - Full processing processes an object and all the objects that it contains. When Process Full is executed against an object that has already been processed, Analysis Services drops all data in the object, and then processes the object. 
  
  - None means no processing is performed.

- **Writeback table options** - If writeback is enabled in the project, this setting defines how writeback is handled. There are three writeback table options:  
  
  - By default, if a writeback table exists, it will be used. If a writeback table does not exist, a new writeback table will be created.  
  
  - If a writeback table already exists, the deployment fails. If a writeback table does not exist, a new writeback table will be created.  
  
  - Regardless of whether a writeback table already exists, a new writeback table will be created. In this case, the Deployment Wizard will delete any existing table and replace it with a new writeback table.  
  
- **Transactional deployment** - This setting controls whether the deployment of metadata changes and process commands occurs in a single transaction or in separate transactions.  
  
  - If this option is **True** (default), [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] deploys all metadata changes and all process commands within a single transaction.  
  
  - If this option is **False**, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] deploys the metadata changes in a single transaction, and deploys each processing command in its own transaction.  
  
### Modifying processing options

 However, you may need to deploy the project using different processing options than those stored in the \<*project name*>.deploymentoptions file. For example, you may want to have all objects fully processed, or processed using the default processing option, or have no processing occur. If the cubes or dimensions are write-enabled, you can specify whether a new or existing writeback table be used.  
  
 To modify the processing options used during deployment, you can either edit and rebuild the project, or change the processing options in the input file by using one of the methods as described in the following procedure.  
  
#### To change processing options after the input files have been generated  
  
- Run the Deployment Wizard interactively. On the **Processing Options** page, specify the processing options for the project being deployed.  
  
     -or-  
  
- Run the Deployment Wizard at the command prompt and set the wizard to run in answer file mode.
  
     -or-  
  
- Modify the \<*project name*>.deploymentoptions file by using any text editor.  

## See also

[Deploy model solutions by using XMLA](deploy-model-solutions-using-xmla.md)  
[Deploy model solutions with the Deployment Utility](deploy-model-solutions-with-the-deployment-utility.md)  
