---
title: "Analysis Services filestore properties | Microsoft Docs"
description:  Learn about the available filestore properties in Analysis Services, like MemoryLimit and PerformanceTrace. 
ms.date: 07/27/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---

# Filestore properties

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Analysis Services includes the following filestore properties. These are all advanced properties that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.

> [!NOTE]
> [MaxOfflineDatasetSizeGB](#maxofflinedatasetsizegb) is the only OLAP property that exclusively applies to Power BI.

## Properties

::: moniker range="power-bi-premium-current"

##### MaxOfflineDatasetSizeGB

Applies to Power BI only. Maximum size of the offline dataset in memory. This is the compressed size on disk. The default value is 0, which is the highest limit defined by SKU. The allowable range is between 0 and the capacity size limit.

::: moniker-end

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

##### MemoryLimit

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MemoryLimitMin

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### PercentScanPerPrice

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### PerformanceTrace

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### RandomFileAccessMode

Does not apply to Power BI. A Boolean property that indicates whether database files and cached files are accessed in random file access mode. This property is off by default. By default, the server does not set the random file access flag when opening partition data files for read access.  
  
On high-end systems, particularly those with large memory resources and multiple NUMA nodes, it can be advantageous to use random file access. In random access mode, Windows bypasses page-mapping operations that read data from disk into the system file cache, thereby lowering contention on the cache.  
  
You will need to run comparison tests to determine whether query performance is improved as the result of changing this property. For best practices on running comparison tests, including clearing the cache and avoiding common mistakes, see the [SQL Server 2008 R2 Analysis Services Operations Guide](/previous-versions/sql/sql-server-2008-r2/hh226085(v=msdn.10)). For additional information on the tradeoffs of using this property, see [https://support.microsoft.com/kb/2549369](https://support.microsoft.com/kb/2549369).  
  
To view or modify this property in SQL Server Management Studio, enable the advanced properties list in the server properties page. You can also change the property in the msmdsrv.ini file. Restarting the server is recommended after setting this property; otherwise files that are already open will continue to be accessed in the previous mode.  
  
##### UnbufferedThreshold

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
## Memory Model category

##### MemoryModel\Tax

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MemoryModel\Income

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MemoryModel\MaximumBalance

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MemoryModel\MinimumBalance

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MemoryModel\InitialBonus

Does not apply to Power BI. An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  

::: moniker-end

## See also

 [Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md)   
 [Determine the Server Mode of an Analysis Services Instance](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
