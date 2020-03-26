---
title: "Analysis Services filestore properties | Microsoft Docs"
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"
---
# Filestore properties

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports the following filestore properties. These are all advanced properties that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.

**Applies to:** Multidimensional and tabular server mode unless noted otherwise.
  
## Properties

 **MemoryLimit**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.  
  
 **MemoryLimitMin**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.  
  
 **PercentScanPerPrice**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.  
  
 **PerformanceTrace**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.  
  
 **RandomFileAccessMode**  
 A Boolean property that indicates whether database files and cached files are accessed in random file access mode. This property is off by default. By default, the server does not set the random file access flag when opening partition data files for read access.  
  
 On high-end systems, particularly those with large memory resources and multiple NUMA nodes, it can be advantageous to use random file access. In random access mode, Windows bypasses page-mapping operations that read data from disk into the system file cache, thereby lowering contention on the cache.  
  
 You will need to run comparison tests to determine whether query performance is improved as the result of changing this property. For best practices on running comparison tests, including clearing the cache and avoiding common mistakes, see the [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539). For additional information on the tradeoffs of using this property, see [https://support.microsoft.com/kb/2549369](https://support.microsoft.com/kb/2549369).  
  
 To view or modify this property in Management Studio, enable the advanced properties list in the server properties page. You can also change the property in the msmdsrv.ini file. Restarting the server is recommended after setting this property; otherwise files that are already open will continue to be accessed in the previous mode.  
  
 **UnbufferedThreshold**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.  
  
## Memory Model category

 **MemoryModel\Tax**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.  
  
 **MemoryModel\Income**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.  
  
 **MemoryModel\MaximumBalance**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.  
  
 **MemoryModel\MinimumBalance**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.  
  
 **MemoryModel\InitialBonus**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.  
  
## See also

 [Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md)   
 [Determine the Server Mode of an Analysis Services Instance](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
