---
title: "Server Properties in Analysis Services | Microsoft Docs"
description: Learn how to modify default server configuration properties of an Azure Analysis Services (Azure AS), SQL Server Analysis Services (SSAS), or Power BI workspace instance.
ms.date: 08/05/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Server properties in Analysis Services

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Administrators can modify many default configuration properties of an Azure Analysis Services (Azure AS) server resource, SQL Server Analysis Services (SSAS) server instance, or a Power BI workspace.

Properties pages in SQL Server Management Studio (SSMS) show a subset of those properties most likely to be modified. For Azure AS and Power BI, all applicable properties can be modified by using XMLA script in SSMS. For SQL Server Analysis Services, all applicable properties can be modified in the msmdsrv.ini file.

> [!NOTE]
> In Power BI, a workspace is effectively an Analysis Services server. In context of Analysis Services, the terms workspace, server, and instance are synonymous.

## Permissions

For Azure AS and SSAS, server administrator permissions are required to modify server properties.

For Power BI, workspace admin permissions are required to modify workspace properties.

## Power BI XMLA-based workspace properties

Power BI workspaces support modifying a limited subset of XMLA-based Analysis Services properties in the General, DAX, Filestore, Memory, and OLAP categories by using SSMS. When modified, the change applies only to that workspace.

Some XMLA-based workspace properties have equivalent capacity settings that can be set in the Admin portal, in **Capacity settings**/**Workloads**/**DATASETS**. These settings apply to *all* workspaces assigned to the capacity, however, workspace admins can override settings for a specific workspace by using SSMS.

|Analysis Services property  |Category | Power BI Capacity setting  |
|---------|---------|---------|
|[AdminTimeOut](general-properties.md#admintimeout)    | General |  NA     |
|[CommitTimeout](general-properties.md#committimeout)     | General |   NA    |
|[DefaultSegmentRowCount](general-properties.md#defaultsegmentrowcount)    |  General |   NA   |
|[ExternalCommandTimeout](general-properties.md#externalcommandtimeout)    |  General |   NA   |
|[ExternalConnectionTimeout](general-properties.md#externalconnectiontimeout)     |  General |   NA   |
|[ForceCommitTimeout](general-properties.md#forcecommittimeout)    |  General |  NA    |
|[MaxIntermediateRowsetSize](dax-properties.md#properties)      | DAX |[Max Intermediate Row Set Count](/power-bi/enterprise/service-admin-premium-workloads?tabs=gen2#max-intermediate-row-set-count) |
|[MaxOfflineDatasetSizeGB](filestore-properties.md#maxofflinedatasetsizegb)     |  Filestore | [Max Offline Dataset Size](/power-bi/enterprise/service-admin-premium-workloads?tabs=gen2#max-offline-dataset-size)       |
|[RowsetSerializationLimit](olap-properties.md#rowsetserializationlimit)        |  OLAP | [Max Result Row Count](/power-bi/enterprise/service-admin-premium-workloads?tabs=gen2#max-result-row-set-count)      |
|[QueryMemoryLimit](memory-properties.md#querymemorylimit)        | Memory | [Query Memory Limit](/power-bi/enterprise/service-admin-premium-workloads?tabs=gen2#query-memory-limit)      |
|[ServerTimeout](general-properties.md#servertimeout)     | General  | [Query Timeout](/power-bi/enterprise/service-admin-premium-workloads?tabs=gen2#query-timeout)      |

Capacity admins can enable or disable the ability for workspace admins to modify XMLA-based workspace property settings. By default, this setting is enabled, meaning workspace admins can modify workspace property settings by using SSMS. Capacity admins can disable this setting in the Admin portal, in **Capacity settings** > **Workloads** > **DATASETS** > **Observe XMLA-based settings**. 

:::image type="content" source="media/pbi-workspace-enable-xmla.png" alt-text="Image of Power BI Workload Datasets settings. ":::

When disabled, workspace admins can't modify *any* XMLA-based property setting.

## Configure by using SQL Server Management Studio
  
1. In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an SSAS, Azure AS, or Power BI instance.  
  
2. In Object Explorer, right-click the instance, and then click **Properties**. The General page appears, displaying the more commonly used properties.  

3. To show more properties, click the **Show Advanced (All) Properties** checkbox at the bottom of the page.

## Configure by using XMLA script

Those properties that can't be set in the Properties page in SSMS or in the msmdrsrv.ini file (SSAS only) can be set by using the [XMLA Alter Element](../xmla/xml-elements-commands/alter-element-xmla.md) in an XMLA script in SSMS.

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

## Configure in msmdsrv.ini
  
For SSAS, server properties are in the msmdsrv.ini file. If the property you want to set isn't visible even after you show advanced properties in SSMS, you might need to edit the msmdsrv.ini file directly. For a default installation, msmdsrv.ini can be found in the \Program Files\Microsoft SQL Server\MSAS13.MSSQLSERVER\OLAP\Config folder.
  
1. Check the **DataDir** property in the General properties page in Management Studio to verify the location of the Analysis Services program files, including the msmdsrv.ini file.

     On a server that has multiple instances, checking the program file location ensures you're modifying the correct file.  
  
2. Navigate to the **config** folder of the program files folder location.

3. Create a backup of the file in case you need to revert to the original file.  
  
4. Use a text editor to view or edit the msmdsrv.ini file.  
  
5. Save the file and restart the service.  

::: moniker-end

## Server property categories  
  
 The following articles describe the various configuration properties:  
  
|Topic|Applies to | Description|  
|-----------|-----------------|-----------------|  
|[General Properties](../../analysis-services/server-properties/general-properties.md)|Azure AS, SSAS, Power BI|General properties are both basic and advanced properties, and include properties that define the data directory, backup directory, and other server behaviors. |  
|[Data Mining Properties](../../analysis-services/server-properties/data-mining-properties.md)|SSAS|Data mining properties control which data mining algorithms are enabled and which are disabled. By default, all of the algorithms are enabled.| 
|[DAX Properties](../../analysis-services/server-properties/dax-properties.md)|Azure AS, SSAS, Power BI|Defines properties related to DAX queries.|
|[Feature Properties](../../analysis-services/server-properties/feature-properties.md)|Azure AS, SSAS|Feature properties pertain to product features, most of them advanced, including properties that control links between server instances.|  
|[Filestore Properties](../../analysis-services/server-properties/filestore-properties.md)|Azure AS, SSAS, Power BI|File store properties are for advanced use only. They include advanced memory management settings.|  
|[Lock Manager Properties](../../analysis-services/server-properties/lock-manager-properties.md)|Azure AS, SSAS|Lock manager properties define server behaviors pertaining to locking and timeouts. Most of these properties are for advanced use only.|  
|[Log Properties](../../analysis-services/server-properties/log-properties.md)|Azure AS, SSAS|Log properties controls if, where, and how events are logged on the server. Includes error logging, exception logging, flight recorder, query logging, and traces.|  
|[Memory Properties](../../analysis-services/server-properties/memory-properties.md)|Azure AS, SSAS, Power BI|Memory properties control how the server uses memory. They're primarily for advanced use.|  
|[Network Properties](../../analysis-services/server-properties/network-properties.md)|Azure AS, SSAS|Network properties control server behavior pertaining to networking, including properties that control compression and binary XML. Most of these properties are for advanced use only.|  
|[OLAP Properties](../../analysis-services/server-properties/olap-properties.md)|Azure AS, SSAS, Power BI|OLAP properties control cube and dimension processing, lazy processing, data caching, and query behavior. Includes both basic and advanced properties.|  
|[Security Properties](../../analysis-services/server-properties/security-properties.md)|Azure AS, SSAS|Security properties contain both basic and advanced properties that define access permissions. Includes settings pertaining to administrators and users.|  
|[Thread Pool Properties](../../analysis-services/server-properties/thread-pool-properties.md)|Azure AS, SSAS|Thread pool properties control how many threads the server creates. These properties are for advanced use only.|  
  
## See also

[Create Analysis Services Scripts in SSMS](../../analysis-services/instances/create-analysis-services-scripts-in-management-studio.md)  
[Analysis Services instance management](../../analysis-services/instances/analysis-services-instance-management.md)  

  