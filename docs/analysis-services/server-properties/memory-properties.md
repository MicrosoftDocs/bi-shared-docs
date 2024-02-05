---
title: "Analysis Services memory properties | Microsoft Docs"
description: Learn about memory properties and how to specify configuration settings so you can control the thresholds at which memory is released.
ms.date: 07/26/2022
ms.service: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Memory properties

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Analysis Services pre-allocates a modest amount of memory at startup so requests can be handled immediately. Additional memory is allocated as query and processing workloads increase. By specifying configuration settings, you can control the thresholds at which memory is released.

> [!NOTE]
> [QueryMemoryLimit](#querymemorylimit) is the only Memory property that applies to Power BI.

::: moniker range=">= sql-analysis-services-2016"

## Default memory configuration

Under the default configuration, each instance allocates a small amount of RAM (40 MB to 50 MB) at startup, even if the instance is idle. Configuration settings are per instance. If you are running multiple instances, such as a tabular and multidimensional instance on the same hardware, each instance will allocate its own memory independently of other instances.

Setting | Description
--------|------------
LowMemoryLimit | For multidimensional instances, a lower threshold at which the server first begins releasing memory allocated to infrequently used objects.
VertiPaqMemoryLimit | For tabular instances, a lower threshold at which the server first begins releasing memory allocated to infrequently used objects.
TotalMemoryLimit | An upper threshold at which Analysis Services begins releasing memory more aggressively to  make room for requests that are in execution as well as new high priority requests. 
HardMemoryLimit | Another threshold at which Analysis Services begins rejecting requests outright due to memory pressure.

::: moniker-end

::: moniker range="asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"

## Properties

Values between 1 and 100 represent percentages of **Total Physical Memory** or **Virtual Address Space**, whichever is less. Values over 100 represent memory limits in bytes.

::: moniker-end

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

##### DefaultPagesCountToReuse

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  

##### HandleIA64AlignmentFaults

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support. 

##### HardMemoryLimit

Specifies a memory threshold after which the instance aggressively terminates active user sessions to reduce memory usage. All terminated sessions will receive an error about being canceled by memory pressure. The default value, zero (0), means the **HardMemoryLimit** will be set to a midway value between **TotalMemoryLimit** and the total physical memory of the system; if the physical memory of the system is larger than the virtual address space of the process, then virtual address space will be used instead to calculate **HardMemoryLimit**. This value isn't configurable for Azure Analysis Services.

##### HeapTypeForObjects

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support. Valid values are as follows:
  
Setting | Description
--------|------------
**-1** | (default) Automatic. The engine will decide which one to use.
**0** | Windows LFH heap.
**1** | Analysis Services slot allocator.
**3** | Each object has its own Analysis Services Heap.

##### HighMemoryPrice

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.

##### LowMemoryLimit

A signed 64-bit double-precision floating-point number property that defines the first threshold at which Analysis Services begins releasing memory for low-priority objects, such as an infrequently used cache. Once the memory is allocated, the server does not release memory below this limit. The default value is 65; which indicates the low memory limit is 65% of physical memory or the virtual address space, whichever is less.  

##### MemoryHeapType

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support. Valid values in SQL Server 2016 SP1 and later Analysis Services are as follows:
  
Setting | Description
--------|------------
**-1** | (default) Automatic. The engine will decide which one to use.
**1** | Analysis Services HEAP.
**2** | Windows LFH.
**5** | Hybrid allocator. This allocator will use Windows LFH for \<= 16 KB allocations and the AS Heap for >16 KB allocations. 
**6** | Intel TBB allocator. Available in SQL Server 2016 SP1 (and later) Analysis Services.

##### MidMemoryPrice

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MinimumAllocatedMemory

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### PreAllocate

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  

::: moniker-end

::: moniker range="asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2019"

##### QueryMemoryLimit

Applies to Power BI, Azure Analysis Services, and SQL Server 2019 and later Analysis Services only. An advanced property to control how much memory can be used during a query.

In SQL Server 2019 and later Analysis Services, this setting applies only to memory spools where intermediate DAX query results are created during query processing. It does not apply to MDX queries.

In Power BI, Azure Analysis Services, and SQL Server 2022 and later Analysis Services, if the **ResourceTrackingEnabled** [Feature property](feature-properties.md) is enabled, this setting is not limited only to memory spools. It applies to all memory utilized by both DAX and MDX queries in tabular mode only.

Specified in percentage up to 100. When more than 100, it's in bytes. Setting a value of 0 means no limit is specified. 

For Azure Analysis Services, the default value is determined by your plan.


|Plan  |Default  |
|---------|---------|
|D1     |      80   |
|All others     |    20     |


::: moniker-end

::: moniker range="asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"

##### SessionMemoryLimit

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  

##### TotalMemoryLimit

Defines a threshold that when reached, causes the server to de-allocate memory to make room for other requests. When this limit is reached, the instance will start to slowly clear memory out of caches by closing expired sessions and unloading unused calculations. For SQL Server Analysis Services, The default value is 80% of physical memory or the virtual address space, whichever is less. The default value for Azure Analysis Services is based on your plan and isn't configurable.  **TotalMemoryLimit** must always be less than **HardMemoryLimit**.

##### VertiPaqMemoryLimit

For tabular instances only, if paging to disk is allowed, this property specifies the level of memory consumption (as a percentage of total memory) at which paging starts. The default is 60. If memory consumption is less than 60 percent, the server will not page to disk. This property depends on the **VertiPaqPagingPolicyProperty**, which must be set to 1 in order for paging to occur.

##### VertiPaqPagingPolicy

For tabular instances only, specifies the paging behavior in the event the server runs low on memory. Valid values are as follows:  
  
Setting  |Description  
---------|---------
**0**     |  (default for Azure Analysis Services and Power BI) Disables paging. If memory is insufficient, processing fails with an out-of-memory error. If you disable paging, you must grant Windows privileges to the service account. See [Configure Service Accounts &#40;Analysis Services&#41;](../../analysis-services/instances/configure-service-accounts-analysis-services.md) for instructions.
**1**     |  (default for SQL Server Analysis Services) This property enables paging to disk using the operating system page file (pagefile.sys).   
  
When set to 1, processing is less likely to fail due to memory constraints because the server will try to page to disk using the method that you specified. Setting the **VertiPaqPagingPolicy** property does not guarantee that memory errors will never happen. Out of memory errors can still occur under the following conditions:  
  
- There is not enough memory for all dictionaries. During processing, the server locks the dictionaries for each column in memory, and all of these together cannot be more than the value specified for **VertiPaqMemoryLimit**.  
  
- There is insufficient virtual address space to accommodate the process.  
  
 To resolve persistent out of memory errors, you can either try to redesign the model to reduce the amount of data that needs processing, or you can add more physical memory to the computer.  
  
##### VirtualMemoryLimit

  An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.
  
##### WaitCountIfHighMemory

 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  

::: moniker-end

## See also

 [Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md)   
 [Determine the Server Mode of an Analysis Services Instance](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
