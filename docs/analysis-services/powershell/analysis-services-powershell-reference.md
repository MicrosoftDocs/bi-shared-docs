---
title: "Analysis Services PowerShell Reference | Microsoft Docs"
description: See a list of the cmdlets corresponding to methods in the Microsoft.AnalysisServices namespace, and links to the corresponding AMO methods.
ms.date: 08/17/2020
ms.service: analysis-services
ms.custom: powershell
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Analysis Services PowerShell Reference
[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] PowerShell cmdlets are included in the [SqlServer module](https://www.powershellgallery.com/packages/SqlServer/21.0.17099). 
  
>[!NOTE] 
> Azure Analysis Services database operations use the same SqlServer module as SQL Server Analysis Services. However, not all cmdlets are supported for Azure Analysis Services. To learn more, see [Manage Azure Analysis Services with PowerShell](/azure/analysis-services/analysis-services-powershell).
  
##  <a name="bkmk_cmdlets"></a> Analysis Services Cmdlets  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides cmdlets correspond to methods in the **Microsoft.AnalysisServices** namespace. The following table describes each cmdlet and provides a link to the corresponding AMO method.  
  
 If you want to use PowerShell to perform a task that is not represented in the following list (for example to create or synchronize a database), you can write TMSL or XMLA script for that action, and then execute it using the **Invoke-ASCmd** cmdlet.  
  
|Cmdlet|Description|Equivalent AMO Methods|  
|------------|-----------------|----------------------------|  
|[Add-RoleMember cmdlet](/powershell/module/sqlserver/Add-RoleMember)|Add a member to a database role.|<xref:Microsoft.AnalysisServices.RoleMemberCollection.Add%2A>|  
|[Backup-ASDatabase cmdlet](/powershell/module/sqlserver/backup-asdatabase)|Backup an Analysis Services database.|[Database.Backup](/dotnet/api/microsoft.analysisservices.database)|  
|[Invoke-ASCmd cmdlet](/powershell/module/sqlserver/invoke-ascmd)|Execute a query or script in XMLA or TSML (JSON) format.|<xref:Microsoft.AnalysisServices.Core.Server.Execute%2A>|  
|[Invoke-ProcessASDatabase](/powershell/module/sqlserver/invoke-processasdatabase)|Process a database.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessCube cmdlet](/powershell/module/sqlserver/invoke-processcube)|Process a cube.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessDimension cmdlet](/powershell/module/sqlserver/invoke-processdimension)|Process a dimension.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessPartition cmdlet](/powershell/module/sqlserver/invoke-processpartition)|Process a partition.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessTable cmdlet](/powershell/module/sqlserver/invoke-processtable)|Process a table in a Tabular model, compatibility model 1200 or higher.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Merge-Partition cmdlet](/powershell/module/sqlserver/merge-partition)|Merge a partition.|<xref:Microsoft.AnalysisServices.Partition.Merge%2A>|  
|[New-RestoreFolder cmdlet](/powershell/module/sqlserver/new-restorefolder)|Create a folder to contain a database backup.|<xref:Microsoft.AnalysisServices.RestoreFolder>|  
|[New-RestoreLocation cmdlet](/powershell/module/sqlserver/new-restorelocation)|Specify one or more remote servers on which to restore the database.|<xref:Microsoft.AnalysisServices.RestoreLocation>|  
|[Remove-RoleMember cmdlet](/powershell/module/sqlserver/remove-rolemember)|Remove a member from a database role.|<xref:Microsoft.AnalysisServices.RoleMemberCollection.Remove%2A>|  
|[Restore-ASDatabase cmdlet](/powershell/module/sqlserver/restore-asdatabase)|Restore a database on a server instance.|<xref:Microsoft.AnalysisServices.Core.Server.Restore%2A>|  
  

  
