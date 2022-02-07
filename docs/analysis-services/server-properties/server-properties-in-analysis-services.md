---
title: "Server Properties in Analysis Services | Microsoft Docs"
description: Learn how to modify default server configuration properties of an Azure Analysis Services (Azure AS) or SQL Server Analysis Services (SSAS) instance.
ms.date: 02/07/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"
---
# Server properties in Analysis Services

[!INCLUDE[ssas-appliesto-sqlas-all-aas](../includes/ssas-appliesto-sqlas-all-aas.md)]

Administrators can modify default server configuration properties of an Azure Analysis Services (Azure AS) or SQL Server Analysis Services (SSAS) instance. To configure server properties, use SQL Server Management Studio.

Properties pages in SQL Server Management Studio show a subset of the properties most likely to be modified.  For SSAS, all properties are in the msmdsrv.ini file. In a default installation, msmdsrv.ini can be found in the \Program Files\Microsoft SQL Server\MSAS13.MSSQLSERVER\OLAP\Config folder.
  
## Configure properties by using SQL Server Management Studio 
  
1.  In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an Azure AS or SSAS instance.  
  
2. In Object Explorer, right-click the instance, and then click **Properties**. The General page appears, displaying the more commonly used properties.  

3.  To view additional properties, click the **Show Advanced (All) Properties** checkbox at the bottom of the page.  
  
     Modifying server properties is supported only for tabular mode and multidimensional mode servers. If you installed [!INCLUDE[ssGeminiShort](../includes/ssgeminishort-md.md)], always use the default values unless otherwise directed otherwise by Microsoft Support.  
  
## Configure properties in msmdsrv.ini
  
Some properties can only be set in the msmdrsrv.ini file. These properties do not apply to Azure Analysis Services.
If the property you want to set is not visible even after you show advanced properties, you might need to edit the msmdsrv.ini file directly. 
  
1.  Check the **DataDir** property in the General property page in Management Studio to verify the location of the Analysis Services program files, including the msmdsrv.ini file.

     On a server that has multiple instances, checking the program file location ensures you're modifying the correct file.  
  
2.  Navigate to the **config** folder of the program files folder location.

3. Create a backup of the file in case you need to revert to the original file.  
  
4.  Use a text editor to view or edit the msmdsrv.ini file.  
  
5.  Save the file and restart the service.  


## Configure properties by using XMLA

Properties that cannot be set by using Properties in SSMS or in msmdrsrv.ini file can be set by using the [XMLA Alter Element](../xmla/xml-elements-commands/alter-element-xmla.md) in an XMLA script in SSMS. 

## Server property categories  
  
 The following topics describe the various [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] configuration properties:  
  
|Topic|Description|  
|-----------|-----------------|  
|[General Properties](../../analysis-services/server-properties/general-properties.md)|The general properties are both basic and advanced properties, and include properties that define the data directory, backup directory, and other server behaviors.|  
|[Data Mining Properties](../../analysis-services/server-properties/data-mining-properties.md)|The data mining properties control which data mining algorithms are enabled and which are disabled. By default, all of the algorithms are enabled.| 
|[DAX Properties](../../analysis-services/server-properties/dax-properties.md)|Defines properties related to DAX queries.|
|DSO|DSO is no longer supported. DSO properties are ignored.|  
|[Feature Properties](../../analysis-services/server-properties/feature-properties.md)|The feature properties pertain to product features, most of them advanced, including properties that control links between server instances.|  
|[Filestore Properties](../../analysis-services/server-properties/filestore-properties.md)|The file store properties are for advanced use only. They include advanced memory management settings.|  
|[Lock Manager Properties](../../analysis-services/server-properties/lock-manager-properties.md)|The lock manager properties define server behaviors pertaining to locking and timeouts. Most of these properties are for advanced use only.|  
|[Log Properties](../../analysis-services/server-properties/log-properties.md)|The log properties controls if, where, and how events are logged on the server. This includes error logging, exception logging, flight recorder, query logging, and traces.|  
|[Memory Properties](../../analysis-services/server-properties/memory-properties.md)|The memory properties control how the server uses memory. They are primarily for advanced use.|  
|[Network Properties](../../analysis-services/server-properties/network-properties.md)|The network properties control server behavior pertaining to networking, including properties that control compression and binary XML. Most of these properties are for advanced use only.|  
|[OLAP Properties](../../analysis-services/server-properties/olap-properties.md)|The OLAP properties control cube and dimension processing, lazy processing, data caching, and query behavior. These include both basic and advanced properties.|  
|[Security Properties](../../analysis-services/server-properties/security-properties.md)|The security section contains both basic and advanced properties that define access permissions. This includes settings pertaining to administrators and users.|  
|[Thread Pool Properties](../../analysis-services/server-properties/thread-pool-properties.md)|The thread pool properties control how many threads the server creates. These are primarily advanced properties.|  
  
## See also

 [Analysis Services instance management](../../analysis-services/instances/analysis-services-instance-management.md)   
 [Deploy by using the Deployment Wizard](../../analysis-services/deployment/deploy-model-solutions-using-the-deployment-wizard.md)  
  