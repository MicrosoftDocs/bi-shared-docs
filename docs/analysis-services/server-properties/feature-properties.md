---
title: "Analysis Services Feature properties | Microsoft Docs"
description: Learn about the available feature properties in Analysis Services, like ManagedCodeEnabled and ComUdfEnabled. 
ms.date: 07/21/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"
---

# Feature properties

[!INCLUDE[appliesto-sqlas-all-aas](../includes/appliesto-sqlas-all-aas.md)]

Feature properties pertain to product features, most of them advanced, including properties that control links between server instances. In Power BI, all Feature properties are Read Only.

## Properties  
  
|Property|Default|Description|  
|--------------|-------------|-----------------|  
|**ManagedCodeEnabled**|1|A Boolean property that indicates whether CLR storage procedures are enabled. Applies to Multidimensional mode server instances only. |  
|**LinkInsideInstanceEnabled**|1|A Boolean property that indicates whether a linked object can be created inside the same server instance. Applies to Multidimensional mode server instances only.|  
|**LinkToOtherInstanceEnabled**|0|A Boolean property that indicates whether objects on remote servers can be linked to. Applies to Multidimensional mode server instances only.|  
|**LinkFromOtherInstanceEnabled**|0|A Boolean property that indicates whether objects can be linked to from other server instances. Applies to Multidimensional mode server instances only.|  
|**ConnStringEncryptionEnabled**|1|A Boolean property that indicates whether the connection string is encrypted in the server configuration file. Applies to Multidimensional mode server instances only.|  
|**UseCachedPageAllocators**|0|A Boolean property that indicates whether cached page allocators are enabled.|  
|**ComUdfEnabled**|0|A Boolean property that indicates whether user-defined functions defined as COM objects are enabled. Applies to Multidimensional mode server instances only.|  
|**SQMSupportEnabled**|1|A Boolean property that indicates whether error and feature usage reports are sent to [!INCLUDE[msCoName](../includes/msconame-md.md)] automatically.|  
|**ResourceMonitoringEnabled**|1|A Boolean property that indicates whether internal resource monitoring counters are enabled. This property is on by default. When enabled, this property allows counters to collect usage data about CPU, memory, and I/O activity.<br /><br /> Internal resource monitoring counters are used by Dynamic Management Views (DMV) that report on resource utilization. If you disable this property, the DMV queries will still run, but the result set will be invalid. DMVs that depend on this property include the following:<br /><br /> **DISCOVER_OBJECT_ACTIVITY**<br /><br /> **DISCOVER_COMMAND_OBJECTS**<br /><br /> **DISCOVER_SESSIONS** (for SESSION_READS, SESSION_WRITES, SESSION_CPU_TIME_MS)<br /><br /> <br /><br /> Note: On a multi-core system that uses NUMA architecture, disabling this property can improve query performance, particularly for high multi-user workloads. You will need to run comparison tests to determine whether query performance is improved as the result of changing this property. For best practices on running comparison tests, including clearing the cache and avoiding common mistakes, see the [SQL Server 2008 R2 Analysis Services Operations Guide](/previous-versions/sql/sql-server-2008-r2/hh226085(v=msdn.10)).|  
|**ResourceTrackingEnabled**|-1|An Integer property that indicates whether resource memory tracking is enabled, which is used to support accurate memory tracking for queries. The following values are supported: -1: Automatic (Enabled); 0: Disabled; 1: Enabled. Applies to SQL Server 2022 and later Analysis Services Tabular server mode only.|
  
## See also

[Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md)   
[Determine the server mode of an Analysis Services instance](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)   
[Use Dynamic Management Views &#40;DMVs&#41; to monitor Analysis Services](../../analysis-services/instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services.md)  
