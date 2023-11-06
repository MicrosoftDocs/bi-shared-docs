---
title: "Discover Events Data Columns | Microsoft Docs"
description: Learn about the Discover Event data classes and Discover Begin class-data columns.
ms.date: 07/19/2021
ms.service: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Discover Events Data Columns

  The Discover Events category has the following event classes:  
  
-   Discover Begin class  
  
-   Discover End class  
  
 The following tables list the data columns for each of these event classes.  
  
## Discover Begin Class—Data Columns  
  
| Column Name | Column Id | Column Type | Column Description |
| ----------- | --------- | ----------- | ------------------ |
|EventClass|0|1|Event Class is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class.  The following are valid **Sub Class Id**/**Sub Class Name** value pairs:<br /> 0: DBSCHEMA_CATALOGS<br /> 1: DBSCHEMA_TABLES<br /> 2: DBSCHEMA_COLUMNS<br /> 3: DBSCHEMA_PROVIDER_TYPES<br /> 4: MDSCHEMA_CUBES<br /> 5: MDSCHEMA_DIMENSIONS<br /> 6: MDSCHEMA_HIERARCHIES<br /> 7: MDSCHEMA_LEVELS<br /> 8: MDSCHEMA_MEASURES<br /> 9: MDSCHEMA_PROPERTIES<br /> 10: MDSCHEMA_MEMBERS<br /> 11: MDSCHEMA_FUNCTIONS<br /> 12: MDSCHEMA_ACTIONS<br /> 13: MDSCHEMA_SETS<br /> 14: DISCOVER_INSTANCES<br /> 15: MDSCHEMA_KPIS<br /> 16: MDSCHEMA_MEASUREGROUPS<br /> 17: MDSCHEMA_COMMANDS<br /> 18: DMSCHEMA_MINING_SERVICES<br /> 19: DMSCHEMA_MINING_SERVICE_PARAMETERS<br /> 20: DMSCHEMA_MINING_FUNCTIONS<br /> 21: DMSCHEMA_MINING_MODEL_CONTENT<br /> 22: DMSCHEMA_MINING_MODEL_XML<br /> 23: DMSCHEMA_MINING_MODELS<br /> 24: DMSCHEMA_MINING_COLUMNS<br /> 25: DISCOVER_DATASOURCES<br /> 26: DISCOVER_PROPERTIES<br /> 27: DISCOVER_SCHEMA_ROWSETS<br /> 28: DISCOVER_ENUMERATORS<br /> 29: DISCOVER_KEYWORDS<br /> 30: DISCOVER_LITERALS<br /> 31: DISCOVER_XML_METADATA<br /> 32: DISCOVER_TRACES<br /> 33: DISCOVER_TRACE_DEFINITION_PROVIDERINFO<br /> 34: DISCOVER_TRACE_COLUMNS<br /> 35: DISCOVER_TRACE_EVENT_CATEGORIES<br /> 36: DMSCHEMA_MINING_STRUCTURES<br /> 37: DMSCHEMA_MINING_STRUCTURE_COLUMNS<br /> 38: DISCOVER_MASTER_KEY<br /> 39: MDSCHEMA_INPUT_DATASOURCES<br /> 40: DISCOVER_LOCATIONS<br /> 41: DISCOVER_PARTITION_DIMENSION_STAT<br /> 42: DISCOVER_PARTITION_STAT<br /> 43: DISCOVER_DIMENSION_STAT<br /> 44: MDSCHEMA_MEASUREGROUP_DIMENSIONS<br /> 45: DISCOVER_XEVENT_PACKAGES<br /> 46: DISCOVER_XEVENT_OBJECTS<br /> 47: DISCOVER_XEVENT_OBJECT_COLUMNS<br /> 48: DISCOVER_XEVENT_SESSION_TARGETS<br /> 49: DISCOVER_XEVENT_SESSIONS<br /> 50: DISCOVER_STORAGE_TABLES<br /> 51: DISCOVER_STORAGE_TABLE_COLUMNS<br /> 52: DISCOVER_STORAGE_TABLE_COLUMN_SEGMENTS<br /> 53: DISCOVER_CALC_DEPENDENCY<br /> 54: DISCOVER_CSDL_METADATA<br /> 55: DISCOVER_RESOURCE_POOLS<br /> 56: TMSCHEMA_MODEL<br /> 57: TMSCHEMA_DATA_SOURCES<br /> 58: TMSCHEMA_TABLES<br /> 59: TMSCHEMA_COLUMNS<br /> 60: TMSCHEMA_ATTRIBUTE_HIERARCHIES<br /> 61: TMSCHEMA_PARTITIONS<br /> 62: TMSCHEMA_RELATIONSHIPS<br /> 63: TMSCHEMA_MEASURES<br /> 64: TMSCHEMA_HIERARCHIES<br /> 65: TMSCHEMA_LEVELS<br /> 67: TMSCHEMA_TABLE_STORAGES<br /> 68: TMSCHEMA_COLUMN_STORAGES<br /> 69: TMSCHEMA_PARTITION_STORAGES<br /> 70: TMSCHEMA_SEGMENT_MAP_STORAGES<br /> 71: TMSCHEMA_DICTIONARY_STORAGES<br /> 72: TMSCHEMA_COLUMN_PARTITION_STORAGES<br /> 73: TMSCHEMA_RELATIONSHIP_STORAGES<br /> 74: TMSCHEMA_RELATIONSHIP_INDEX_STORAGES<br /> 75: TMSCHEMA_ATTRIBUTE_HIERARCHY_STORAGES<br /> 76: TMSCHEMA_HIERARCHY_STORAGES<br /> 77: DISCOVER_RING_BUFFERS<br /> 78: TMSCHEMA_KPIS<br /> 79: TMSCHEMA_STORAGE_FOLDERS<br /> 80: TMSCHEMA_STORAGE_FILES<br /> 81: TMSCHEMA_SEGMENT_STORAGES<br /> 82: TMSCHEMA_CULTURES<br /> 83: TMSCHEMA_OBJECT_TRANSLATIONS<br /> 84: TMSCHEMA_LINGUISTIC_METADATA<br /> 85: TMSCHEMA_ANNOTATIONS<br /> 86: TMSCHEMA_PERSPECTIVES<br /> 87: TMSCHEMA_PERSPECTIVE_TABLES<br /> 88: TMSCHEMA_PERSPECTIVE_COLUMNS<br /> 89: TMSCHEMA_PERSPECTIVE_HIERARCHIES<br /> 90: TMSCHEMA_PERSPECTIVE_MEASURES<br />  95: TMSCHEMA_SETS<br /> 96: TMSCHEMA_PERSPECTIVE_SETS<br /> 97: TMSCHEMA_EXTENDED_PROPERTIES<br /> 98: TMSCHEMA_EXPRESSIONS<br /> 99: TMSCHEMA_COLUMN_PERMISSIONS<br /> 100: TMSCHEMA_DETAIL_ROWS_DEFINITIONS<br /> 101: TMSCHEMA_RELATED_COLUMN_DETAILS<br /> 102: TMSCHEMA_GROUP_BY_COLUMNS<br /> 103: TMSCHEMA_CALCULATION_GROUPS<br /> 104: TMSCHEMA_CALCULATION_ITEMS<br /> 105: TMSCHEMA_ALTERNATE_OF_DEFINITIONS<br /> 106: TMSCHEMA_REFRESH_POLICIES<br /> 107: DISCOVER_POWERBI_DATASOURCES<br /> 108: TMSCHEMA_FORMAT_STRING_DEFINITIONS<br /> 109: DISCOVER_M_EXPRESSIONS<br /> 110: TMSCHEMA_POWERBI_ROLES<br /> 111: TMSCHEMA_QUERY_GROUPS<br /> 112: DISCOVER_DB_MEM_STATS<br /> 113: DISCOVER_MEM_STATS<br /> 114: TMSCHEMA_ANALYTICS_AIMETADATA<br /> 115: DISCOVER_OBJECT_COUNTERS<br />  |  
|CurrentTime|2|5|Time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the discover event.|  
|DatabaseName|28|8|Name of the database in which the statement of the user is running.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|  
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Microsoft Entra accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|ClientProcessID|36|1|Contains the process ID of the client application.|  
|ApplicationName|37|8|Name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|  
|SessionID|39|8|Contains the session ID associated with the discover event.|  
|NTCanonicalUserName|40|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the discover event. The SPID directly corresponds to the session GUID used by XMLA.|  
|TextData|42|9|Contains the text data associated with the event.|  
|ServerName|43|8|Contains the name of the instance on which the discover event occurred.|  
|RequestProperties|45|9|Contains the XML for Analysis (XMLA) request properties associated with the discover event.|  
  
## Discover End Class—Data Columns  
  
| Column Name | Column Id | Column Type | Column Description |
| ----------- | --------- | ----------- | ------------------ |
|EventClass|0|1|Contains the event class; this is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class. The following are valid **Sub Class Id**/**Sub Class Name** value pairs:<br /> 0: DBSCHEMA_CATALOGS<br /> 1: DBSCHEMA_TABLES<br /> 2: DBSCHEMA_COLUMNS<br /> 3: DBSCHEMA_PROVIDER_TYPES<br /> 4: MDSCHEMA_CUBES<br /> 5: MDSCHEMA_DIMENSIONS<br /> 6: MDSCHEMA_HIERARCHIES<br /> 7: MDSCHEMA_LEVELS<br /> 8: MDSCHEMA_MEASURES<br /> 9: MDSCHEMA_PROPERTIES<br /> 10: MDSCHEMA_MEMBERS<br /> 11: MDSCHEMA_FUNCTIONS<br /> 12: MDSCHEMA_ACTIONS<br /> 13: MDSCHEMA_SETS<br /> 14: DISCOVER_INSTANCES<br /> 15: MDSCHEMA_KPIS<br /> 16: MDSCHEMA_MEASUREGROUPS<br /> 17: MDSCHEMA_COMMANDS<br /> 18: DMSCHEMA_MINING_SERVICES<br /> 19: DMSCHEMA_MINING_SERVICE_PARAMETERS<br /> 20: DMSCHEMA_MINING_FUNCTIONS<br /> 21: DMSCHEMA_MINING_MODEL_CONTENT<br /> 22: DMSCHEMA_MINING_MODEL_XML<br /> 23: DMSCHEMA_MINING_MODELS<br /> 24: DMSCHEMA_MINING_COLUMNS<br /> 25: DISCOVER_DATASOURCES<br /> 26: DISCOVER_PROPERTIES<br /> 27: DISCOVER_SCHEMA_ROWSETS<br /> 28: DISCOVER_ENUMERATORS<br /> 29: DISCOVER_KEYWORDS<br /> 30: DISCOVER_LITERALS<br /> 31: DISCOVER_XML_METADATA<br /> 32: DISCOVER_TRACES<br /> 33: DISCOVER_TRACE_DEFINITION_PROVIDERINFO<br /> 34: DISCOVER_TRACE_COLUMNS<br /> 35: DISCOVER_TRACE_EVENT_CATEGORIES<br /> 36: DMSCHEMA_MINING_STRUCTURES<br /> 37: DMSCHEMA_MINING_STRUCTURE_COLUMNS<br /> 38: DISCOVER_MASTER_KEY<br /> 39: MDSCHEMA_INPUT_DATASOURCES<br /> 40: DISCOVER_LOCATIONS<br /> 41: DISCOVER_PARTITION_DIMENSION_STAT<br /> 42: DISCOVER_PARTITION_STAT<br /> 43: DISCOVER_DIMENSION_STAT<br /> 44: MDSCHEMA_MEASUREGROUP_DIMENSIONS<br /> 45: DISCOVER_XEVENT_PACKAGES<br /> 46: DISCOVER_XEVENT_OBJECTS<br /> 47: DISCOVER_XEVENT_OBJECT_COLUMNS<br /> 48: DISCOVER_XEVENT_SESSION_TARGETS<br /> 49: DISCOVER_XEVENT_SESSIONS<br /> 50: DISCOVER_STORAGE_TABLES<br /> 51: DISCOVER_STORAGE_TABLE_COLUMNS<br /> 52: DISCOVER_STORAGE_TABLE_COLUMN_SEGMENTS<br /> 53: DISCOVER_CALC_DEPENDENCY<br /> 54: DISCOVER_CSDL_METADATA<br /> 55: DISCOVER_RESOURCE_POOLS<br /> 56: TMSCHEMA_MODEL<br /> 57: TMSCHEMA_DATA_SOURCES<br /> 58: TMSCHEMA_TABLES<br /> 59: TMSCHEMA_COLUMNS<br /> 60: TMSCHEMA_ATTRIBUTE_HIERARCHIES<br /> 61: TMSCHEMA_PARTITIONS<br /> 62: TMSCHEMA_RELATIONSHIPS<br /> 63: TMSCHEMA_MEASURES<br /> 64: TMSCHEMA_HIERARCHIES<br /> 65: TMSCHEMA_LEVELS<br /> 67: TMSCHEMA_TABLE_STORAGES<br /> 68: TMSCHEMA_COLUMN_STORAGES<br /> 69: TMSCHEMA_PARTITION_STORAGES<br /> 70: TMSCHEMA_SEGMENT_MAP_STORAGES<br /> 71: TMSCHEMA_DICTIONARY_STORAGES<br /> 72: TMSCHEMA_COLUMN_PARTITION_STORAGES<br /> 73: TMSCHEMA_RELATIONSHIP_STORAGES<br /> 74: TMSCHEMA_RELATIONSHIP_INDEX_STORAGES<br /> 75: TMSCHEMA_ATTRIBUTE_HIERARCHY_STORAGES<br /> 76: TMSCHEMA_HIERARCHY_STORAGES<br /> 77: DISCOVER_RING_BUFFERS<br /> 78: TMSCHEMA_KPIS<br /> 79: TMSCHEMA_STORAGE_FOLDERS<br /> 80: TMSCHEMA_STORAGE_FILES<br /> 81: TMSCHEMA_SEGMENT_STORAGES<br /> 82: TMSCHEMA_CULTURES<br /> 83: TMSCHEMA_OBJECT_TRANSLATIONS<br /> 84: TMSCHEMA_LINGUISTIC_METADATA<br /> 85: TMSCHEMA_ANNOTATIONS<br /> 86: TMSCHEMA_PERSPECTIVES<br /> 87: TMSCHEMA_PERSPECTIVE_TABLES<br /> 88: TMSCHEMA_PERSPECTIVE_COLUMNS<br /> 89: TMSCHEMA_PERSPECTIVE_HIERARCHIES<br /> 90: TMSCHEMA_PERSPECTIVE_MEASURES<br />  95: TMSCHEMA_SETS<br /> 96: TMSCHEMA_PERSPECTIVE_SETS<br /> 97: TMSCHEMA_EXTENDED_PROPERTIES<br /> 98: TMSCHEMA_EXPRESSIONS<br /> 99: TMSCHEMA_COLUMN_PERMISSIONS<br /> 100: TMSCHEMA_DETAIL_ROWS_DEFINITIONS<br /> 101: TMSCHEMA_RELATED_COLUMN_DETAILS<br /> 102: TMSCHEMA_GROUP_BY_COLUMNS<br /> 103: TMSCHEMA_CALCULATION_GROUPS<br /> 104: TMSCHEMA_CALCULATION_ITEMS<br /> 105: TMSCHEMA_ALTERNATE_OF_DEFINITIONS<br /> 106: TMSCHEMA_REFRESH_POLICIES<br /> 107: DISCOVER_POWERBI_DATASOURCES<br /> 108: TMSCHEMA_FORMAT_STRING_DEFINITIONS<br /> 109: DISCOVER_M_EXPRESSIONS<br /> 110: TMSCHEMA_POWERBI_ROLES<br /> 111: TMSCHEMA_QUERY_GROUPS<br /> 112: DISCOVER_DB_MEM_STATS<br /> 113: DISCOVER_MEM_STATS<br /> 114: TMSCHEMA_ANALYTICS_AIMETADATA<br /> 115: DISCOVER_OBJECT_COUNTERS<br />  |  
|CurrentTime|2|5|Contains the current time of the discover event, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contains the time (if available) at which the discover end event started.. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|EndTime|4|5|Contains the time at which the event ended. This column is not populated for starting event classes, such as SQL:BatchStarting or SP:Starting. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|Duration|5|2|Contains the approximate amount of time (milliseconds) taken by the discover event.|  
|CPUTime|6|2|Contains the amount of CPU time (in milliseconds) used by the event.|  
|Severity|22|1|Contains the severity level of an exception.|  
|Success|23|1|Contains the success or failure of the discover event. Values are:<br /><br /> 0 = Failure<br /><br /> 1 = Success|  
|Error|24|1|Contains the error number of any error associated the discover event.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the discover event.|  
|DatabaseName|28|8|Contains the name of the database in which the discover event occurred.|  
|NTUserName|32|8|Contains the Windows user name associated with the object permission event.|  
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Microsoft Entra accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|ClientProcessID|36|1|Contains the client process ID of the application that initiated the event.|  
|ApplicationName|37|8|Contains the name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|  
|SessionID|39|8|Contains the session ID associated with the discover event.|  
|NTCanonicalUserName|40|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the discover end event. The SPID directly corresponds to the session GUID used by XMLA.|  
|TextData|42|9|Contains the text data associated with the event.|  
|ServerName|43|8|Contains the name of the instance on which the discover event occurred.|  
|RequestProperties|45|9|Contains the properties in the XMLA request.|  
  
  
  
