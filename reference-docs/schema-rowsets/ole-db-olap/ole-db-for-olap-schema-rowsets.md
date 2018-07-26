---
title: "OLE DB for OLAP Schema Rowsets | Microsoft Docs"
ms.date: 07/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: schema-rowsets
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# OLE DB for OLAP Schema Rowsets

  The Microsoft XML for Analysis (XMLA) provider supports the following OLE DB for OLAP schema rowsets.  
  
> [!NOTE]  
>  To check whether a particular data source provider supports a rowset, use the **DISCOVER_ENUMERATIONS** rowset with the [Discover](../../xmla/xml-elements-methods-discover.md) method.  
  
 You can also find detailed information about these rowsets by searching for the topic, "OLAP Schema Rowsets," in the MSDN Library at this [Microsoft Web site](http://go.microsoft.com/fwlink/?LinkId=15426).  
  
## In This Section  
  
|Schema Rowset<sup>1</sup>|Description|  
|-------------------------------|-----------------|  
|[DISCOVER_INSTANCES Rowset](discover-instances-rowset.md)|Describes the instances on the server.|  
|[DISCOVER_KEYWORDS Rowset &#40;OLE DB for OLAP&#41;](discover-keywords-rowset-ole-db-for-olap.md)|Enumerates a list of words reserved by the provider.|  
|[MDSCHEMA_ACTIONS Rowset](mdschema-actions-rowset.md)|Describes the actions that may be available to the client application.|  
|[MDSCHEMA_CUBES Rowset](mdschema-cubes-rowset.md)|Describes the structure of cubes within a database.|  
|[MDSCHEMA_DIMENSIONS Rowset](mdschema-dimensions-rowset.md)|Describes the shared and private dimensions within a database.|  
|[MDSCHEMA_FUNCTIONS Rowset](mdschema-functions-rowset.md)|Describes the functions that are available to client applications connected to the database.|  
|[MDSCHEMA_HIERARCHIES Rowset](mdschema-hierarchies-rowset.md)|Describes each hierarchy that is contained in a particular dimension.|  
|[MDSCHEMA_INPUT_DATASOURCES Rowset](mdschema-input-datasources-rowset.md)|Describes the data sources defined within the database.|  
|[MDSCHEMA_KPIS Rowset](mdschema-kpis-rowset.md)|Describes the key performance indicators (KPIs) within a database.|  
|[MDSCHEMA_LEVELS Rowset](mdschema-levels-rowset.md)|Describes each level within a particular hierarchy.|  
|[MDSCHEMA_MEASUREGROUP_DIMENSIONS Rowset](mdschema-measuregroup-dimensions-rowset.md)|Enumerates the dimensions of measure groups.|  
|[MDSCHEMA_MEASUREGROUPS Rowset](mdschema-measuregroups-rowset.md)|Describes the measure groups within a database.|  
|[MDSCHEMA_MEASURES Rowset](mdschema-measures-rowset.md)|Describes each measure within in a cube.|  
|[MDSCHEMA_MEMBERS Rowset](mdschema-members-rowset.md)|Describes the members within a database.|  
|[MDSCHEMA_PROPERTIES Rowset](mdschema-properties-rowset.md)|Describes the properties of members within in a database.|  
|[MDSCHEMA_SETS Rowset](mdschema-sets-rowset.md)|Describes any sets that are currently defined in a database, including session-scoped sets.|  
  
 <sup>1</sup> All the schema rowsets listed here are supported by the MSOLAP data source provider for the Microsoft XMLA provider.  
