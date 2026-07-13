---
title: "Backup Options (Analysis Services multidimensional) | Microsoft Docs"
description: Learn about backup and synchronization options for Microsoft SQL Server Analysis Services databases.
ms.date: 05/02/2018
ms.service: azure-analysis-services
ms.custom: multidimensional-models
ms.topic: concept-article

---
# Backup options
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  You can back up your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] databases in many ways. All methods require server administrator and database administrator permissions. You can open the **Backup** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], select the appropriate options, and then run the backup from the dialog box. Or, you can create a script using the settings already specified in the file. You can save and run the script as frequently as required.  
  
## Backup and synchronize  
 If the database is on a remote instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you can use the synchronization feature to back up the database to the local instance. You can move development builds of a database into production by using this feature. You can also use conventional, file-based, backup and restore to move the development build into production. However, synchronization provides extra functionality. For example, you can have security settings that are different for the development and production computers. Synchronization gives you the option to maintain those settings and synchronize all objects other than roles. Also, synchronization typically does an incremental update of those objects that are different for the source and destination computers. This kind of incremental backup isn't available by using the backup/restore feature. For more information, see [Synchronize Analysis Services Databases](../../analysis-services/multidimensional-models/synchronize-analysis-services-databases.md).  
  
> [!IMPORTANT]  
>  The Analysis Services service account must have permission to write to the backup location that you specify for each file. Also, you must have one of the following roles: administrator role on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to back up.  
  
## See also  
 [Backup Database Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../analysis-services-overview.md?viewFallbackFrom=sql-server-ver15)   
 [Backup and Restore of Analysis Services Databases](../../analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases.md)   
 [Backup Element &#40;XMLA&#41;](../xmla/xml-elements-commands/backup-element-xmla.md)   
 [Backing Up, Restoring, and Synchronizing Databases &#40;XMLA&#41;](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md)  
  
