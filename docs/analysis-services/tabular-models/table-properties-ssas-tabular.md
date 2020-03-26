---
title: "Analysis Services tabular model table properties | Microsoft Docs"
ms.date: 01/29/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Table Properties

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](../../includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

The properties described here are different from those in the Edit Table Properties dialog box, which define which columns from the source are imported.  
  
##  <a name="bkmk_properties"></a> Table Properties  
 **Basic**  
  
|Property|Default Setting|Description|  
|--------------|---------------------|-----------------|  
|**Connection Name**|\<connection name>|The name of the connection to the table's data source.<br /><br /> To edit the connection, click the button.|  
|**Hidden**|False|Specifies whether the table is hidden from reporting client field lists.|  
|**Partitions**||Partitions for the table cannot be displayed in the **Properties** window. To view, create, or edit partitions, click the button to open the Partition Manager.|  
|**Source Data**||Source data for the table cannot be displayed in the **Properties** window. To view or edit the source data, click the button to open the Edit Table Properties dialog box.|  
|**Table Description**||A text description for the table.<br /><br /> In [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], if an end-user places the cursor over this table in the field list, the description appears as a tooltip.|  
|**Table Name**|\<friendly name>|Specifies the table's friendly name. The table name can be specified when a table is imported using the Table Import Wizard or at any time after import. The table name in the model can be different from the associated table at the source. The table friendly name appears in the reporting client application field list as well as in the model database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].|  
  
 **Reporting Properties**  
  
|Property|Default Setting|Description|  
|--------------|---------------------|-----------------|  
|**Default Field Set**|||  
|Table Behavior|||  
  
##  <a name="bkmk_config_prop"></a> Configure table property settings  
  
1.  In the model designer, in Data View, click a table (tab), or, in Diagram View, click a table header.  
  
2.  In the **Properties** window, click on a property, and then type a value or click the button for additional configuration options.  
  
  
