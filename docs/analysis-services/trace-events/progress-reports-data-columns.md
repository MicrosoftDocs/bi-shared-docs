---
title: "Progress Reports Data Columns | Microsoft Docs"
description: Learn about the data columns for the Progress Reports event category.
ms.date: 07/19/2021
ms.service: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Progress Reports Data Columns

  The Progress Reports event category has the following event classes:  
  
|**Event ID**|**Event Name**|**Event Description**|  
|------------------|--------------------|---------------------------|  
|5|Progress Report Begin|Progress report begin.|  
|6|Progress Report End|Progress report end.|  
|7|Progress Report Current|Progress report current.|  
|8|Progress Report Error|Progress report error.|  
  
 The following tables list the data columns for each of these event classes.  
  
## Progress Report Begin–Data Columns  
  
|**Column Name**|**Column Id**|**Column Type**|**Column Description**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Event Class is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class. The following are valid **Sub Class Id**: **Sub Class Name** pairs:<br /><br /> 1: **Process**<br /><br /> 2: **Merge**<br /><br /> 3: **Delete**<br /><br /> 4: **DeleteOldAggregations**<br /><br /> 5: **Rebuild**<br /><br /> 6: **Commit**<br /><br /> 7: **Rollback**<br /><br /> 8: **CreateIndexes**<br /><br /> 9: **CreateTable**<br /><br /> 10: **InsertInto**<br /><br /> 11: **Transaction**<br /><br /> 12: **Initialize**<br /><br /> 13: **Discretize**<br /><br /> 14: **Query**<br /><br /> 15: **CreateView**<br /><br /> 16: **WriteData**<br /><br /> 17: **ReadData**<br /><br /> 18: **GroupData**<br /><br /> 19: **GroupDataRecord**<br /><br /> 20: **BuildIndex**<br /><br /> 21: **Aggregate**<br /><br /> 22: **BuildDecode**<br /><br /> 23: **WriteDecode**<br /><br /> 24: **BuildDMDecode**<br /><br /> 25: **ExecuteSQL**<br /><br /> 26: **ExecuteModifiedSQL**<br /><br /> 27: **Connecting**<br /><br /> 28: **BuildAggsAndIndexes**<br /><br /> 29: **MergeAggsOnDisk**<br /><br /> 30: **BuildIndexForRigidAggs**<br /><br /> 31: **BuildIndexForFlexibleAggs**<br /><br /> 32: **WriteAggsAndIndexes**<br /><br /> 33: **WriteSegment**<br /><br /> 34: **DataMiningProgress**<br /><br /> 35: **ReadBufferFullReport**<br /><br /> 36: **ProactiveCacheConversion**<br /><br /> 37: **Backup**<br /><br /> 38: **Restore**<br /><br /> 39: **Synchronize**<br /><br /> 40: **Build Processing Schedule**<br /><br /> 41: **Detach**<br /><br /> 42: **Attach**<br /><br /> 43: **Analyze\Encode Data**<br /><br /> 44: **Compress Segment**<br /><br /> 45: **Write Table Column**<br /><br /> 46: **Relationship Build Prepare**<br /><br /> 47: **Build Relationship Segment**<br /><br /> 48: **Load**<br /><br /> 49: **Metadata Load**<br /><br /> 50: **Data Load**<br /><br /> 51: **Post Load**<br /><br /> 52: **Metadata traversal during Backup**<br /><br /> 53: **VertiPaq**<br /><br /> 54: **Hierarchy processing**<br /><br /> 55: **Switching dictionary**<br /><br /> 57: **Tabular transaction commit**<br /><br /> 58: **Sequence point**<br /><br /> 59: **Tabular object processing**<br /><br /> 60: **Saving database**<br /><br /> 61: **Tokenization store processing**<br /><br /> 63: **Check segment indexes**<br /><br /> 64: **Check tabular data structure**<br /><br /> 65: **Check column data for duplicates or null values**|  
|CurrentTime|2|5|Contains the current time of the reported event, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contains the time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|JobID|7|1|Contains the job ID associated with the reported event.|  
|SessionType|8|8|Contains the session type (the entity causing the event) associated with the reported event. For processing events, values are:<br /><br /> 1= User<br /><br /> 2= Proactive Caching<br /><br /> 3= Lazy processing|  
|ObjectID|11|8|Contains the object ID (a string) associated with the reported event.|  
|ObjectType|12|1|Contains the object type.|  
|ObjectName|13|8|Contains the name of the object associated with the reported event.|  
|ObjectPath|14|8|Contains the object path for the object associated with the reported event, as a comma-separated list of parents starting with the object's parents.|  
|ObjectReference|15|8|Contains the object reference for the reported event, encoded as XML for all parents and using tags to describe the object.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the reported event.|  
|DatabaseName|28|8|Contains the name of the database in which the reported event occurred.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|  
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Microsoft Entra accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|SessionID|39|8|Contains the session ID associated with the reported event.|  
|NTCanonicalUserName|40|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the reported event. The SPID directly corresponds to the session GUID used by XML for Analysis (XMLA).|  
|TextData|42|9|Contains the text data associated with the reported event.|  
|ServerName|43|8|Contains the name of the instance on which the reported event occurred.|  
  
## Progress Report End–Data Columns  
  
|**Column Name**|**Column Id**|**Column Type**|**Column Description**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Event Class is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class. The following are valid **Sub Class Id**: **Sub Class Name** pairs:<br /><br /> 1: **Process**<br /><br /> 2: **Merge**<br /><br /> 3: **Delete**<br /><br /> 4: **DeleteOldAggregations**<br /><br /> 5: **Rebuild**<br /><br /> 6: **Commit**<br /><br /> 7: **Rollback**<br /><br /> 8: **CreateIndexes**<br /><br /> 9: **CreateTable**<br /><br /> 10: **InsertInto**<br /><br /> 11: **Transaction**<br /><br /> 12: **Initialize**<br /><br /> 13: **Discretize**<br /><br /> 14: **Query**<br /><br /> 15: **CreateView**<br /><br /> 16: **WriteData**<br /><br /> 17: **ReadData**<br /><br /> 18: **GroupData**<br /><br /> 19: **GroupDataRecord**<br /><br /> 20: **BuildIndex**<br /><br /> 21: **Aggregate**<br /><br /> 22: **BuildDecode**<br /><br /> 23: **WriteDecode**<br /><br /> 24: **BuildDMDecode**<br /><br /> 25: **ExecuteSQL**<br /><br /> 26: **ExecuteModifiedSQL**<br /><br /> 27: **Connecting**<br /><br /> 28: **BuildAggsAndIndexes**<br /><br /> 29: **MergeAggsOnDisk**<br /><br /> 30: **BuildIndexForRigidAggs**<br /><br /> 31: **BuildIndexForFlexibleAggs**<br /><br /> 32: **WriteAggsAndIndexes**<br /><br /> 33: **WriteSegment**<br /><br /> 34: **DataMiningProgress**<br /><br /> 35: **ReadBufferFullReport**<br /><br /> 36: **ProactiveCacheConversion**<br /><br /> 37: **Backup**<br /><br /> 38: **Restore**<br /><br /> 39: **Synchronize**<br /><br /> 40: **Build Processing Schedule**<br /><br /> 41: **Detach**<br /><br /> 42: **Attach**<br /><br /> 43: **Analyze\Encode Data**<br /><br /> 44: **Compress Segment**<br /><br /> 45: **Write Table Column**<br /><br /> 46: **Relationship Build Prepare**<br /><br /> 47: **Build Relationship Segment**<br /><br /> 48: **Load**<br /><br /> 49: **Metadata Load**<br /><br /> 50: **Data Load**<br /><br /> 51: **Post Load**<br /><br /> 52: **Metadata traversal during Backup**<br /><br /> 53: **VertiPaq**<br /><br /> 54: **Hierarchy processing**<br /><br /> 55: **Switching dictionary**<br /><br /> 57: **Tabular transaction commit**<br /><br /> 58: **Sequence point**<br /><br /> 59: **Tabular object processing**<br /><br /> 60: **Saving database**<br /><br /> 61: **Tokenization store processing**<br /><br /> 63: **Check segment indexes**<br /><br /> 64: **Check tabular data structure**<br /><br /> 65: **Check column data for duplicates or null values**<br /><br /> 66: **Analyze refresh policy impact for tabular partition**<br /><br /> 67: **Parallel session**<br /><br /> 68: **Auto aggs training**<br /><br /> 69: **AutoAggs cardinality analysis**<br /><br /> 70: **Export**|  
|CurrentTime|2|5|Contains the current time of the reported event, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contains the time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|EndTime|4|5|Contains the time at which the event ended. This column is not populated for starting event classes, such as SQL:BatchStarting or SP:Starting. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|Duration|5|2|Contains the elapsed amount of time (in milliseconds) taken by the event.|  
|CPUTime|6|2|Contains the amount of CPU time (in milliseconds) used by the event.|  
|JobID|7|1|Contains the job ID associated with the reported event.|  
|SessionType|8|8|Contains the session type (the entity causing the event) associated with the reported event. For processing events, values are:<br /><br /> 1= User<br /><br /> 2= Proactive Caching<br /><br /> 3= Lazy processing|  
|ProgressTotal|9|1|Contains the progress total for the reported event.|  
|IntegerData|10|1|Contains the integer data associated with the reported event, such as the current count of the number of rows processed for a processing event.|  
|ObjectID|11|8|Contains the object ID (a string) associated with the reported event.|  
|ObjectType|12|1|Contains the object type.|  
|ObjectName|13|8|Contains the name of the object associated with the reported event.|  
|ObjectPath|14|8|Contains the object path for the object associated with the reported event, as a comma-separated list of parents starting with the object's parents.|  
|ObjectReference|15|8|Contains the object reference for the reported event, encoded as XML for all parents and using tags to describe the object.|  
|Severity|22|1|Contains the severity level of an exception associated the reported event. Values are:<br /><br /> 0 = Success<br /><br /> 1 = Informational<br /><br /> 2 = Warning<br /><br /> 3 = Error|  
|Success|23|1|Contains the success or failure of the server reported event. Values are:<br /><br /> 0 = Failure<br /><br /> 1 = Success|  
|Error|24|1|Contains the error number of a given event.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the reported event.|  
|DatabaseName|28|8|Contains the name of the database in which the reported event occurred.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|  
|NTDomainName|33|8|Contains the Windows domain account associated with the reported event.|  
|SessionID|39|8|Contains the session ID associated with the reported event.|  
|NTCanonicalUserName|40|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the reported event. The SPID directly corresponds to the session GUID used by XML for Analysis (XMLA).|  
|TextData|42|9|Contains the text data associated with the reported event.|  
|ServerName|43|8|Contains the name of the instance on which the reported event occurred.|  
  
## Progress Report Current–Data Columns  
  
|**Column Name**|**Column Id**|**Column Type**|**Column Description**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Event Class is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class. The following are valid **Sub Class Id**: **Sub Class Name** pairs:<br /><br /> 1: **Process**<br /><br /> 2: **Merge**<br /><br /> 3: **Delete**<br /><br /> 4: **DeleteOldAggregations**<br /><br /> 5: **Rebuild**<br /><br /> 6: **Commit**<br /><br /> 7: **Rollback**<br /><br /> 8: **CreateIndexes**<br /><br /> 9: **CreateTable**<br /><br /> 10: **InsertInto**<br /><br /> 11: **Transaction**<br /><br /> 12: **Initialize**<br /><br /> 13: **Discretize**<br /><br /> 14: **Query**<br /><br /> 15: **CreateView**<br /><br /> 16: **WriteData**<br /><br /> 17: **ReadData**<br /><br /> 18: **GroupData**<br /><br /> 19: **GroupDataRecord**<br /><br /> 20: **BuildIndex**<br /><br /> 21: **Aggregate**<br /><br /> 22: **BuildDecode**<br /><br /> 23: **WriteDecode**<br /><br /> 24: **BuildDMDecode**<br /><br /> 25: **ExecuteSQL**<br /><br /> 26: **ExecuteModifiedSQL**<br /><br /> 27: **Connecting**<br /><br /> 28: **BuildAggsAndIndexes**<br /><br /> 29: **MergeAggsOnDisk**<br /><br /> 30: **BuildIndexForRigidAggs**<br /><br /> 31: **BuildIndexForFlexibleAggs**<br /><br /> 32: **WriteAggsAndIndexes**<br /><br /> 33: **WriteSegment**<br /><br /> 34: **DataMiningProgress**<br /><br /> 35: **ReadBufferFullReport**<br /><br /> 36: **ProactiveCacheConversion**<br /><br /> 37: **Backup**<br /><br /> 38: **Restore**<br /><br /> 39: **Synchronize**<br /><br /> 40: **Build Processing Schedule**<br /><br /> 41: **Detach**<br /><br /> 42: **Attach**<br /><br /> 43: **Analyze\Encode Data**<br /><br /> 44: **Compress Segment**<br /><br /> 45: **Write Table Column**<br /><br /> 46: **Relationship Build Prepare**<br /><br /> 47: **Build Relationship Segment**<br /><br /> 48: **Load**<br /><br /> 49: **Metadata Load**<br /><br /> 50: **Data Load**<br /><br /> 51: **Post Load**<br /><br /> 52: **Metadata traversal during Backup**<br /><br /> 53: **VertiPaq**<br /><br /> 54: **Hierarchy processing**<br /><br /> 55: **Switching dictionary**<br /><br /> 57: **Tabular transaction commit**<br /><br /> 58: **Sequence point**<br /><br /> 59: **Tabular object processing**<br /><br /> 60: **Saving database**<br /><br /> 61: **Tokenization store processing**<br /><br /> 63: **Check segment indexes**<br /><br /> 64: **Check tabular data structure**<br /><br /> 65: **Check column data for duplicates or null values**|  
|CurrentTime|2|5|Contains the current time of the reported event, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contains the time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|JobID|7|1|Contains the job ID associated with the reported event.|  
|SessionType|8|8|Contains the session type (the entity causing the event) associated with the reported event. For processing events, values are:<br /><br /> 1= User<br /><br /> 2= Proactive Caching<br /><br /> 3= Lazy processing|  
|ProgressTotal|9|1|Contains the progress total for the reported event.|  
|IntegerData|10|1|Contains the integer data associated with the reported event, such as the current count of the number of rows processed for a processing event.|  
|ObjectID|11|8|Contains the object ID (a string) associated with the reported event.|  
|ObjectType|12|1|Contains the object type.|  
|ObjectName|13|8|Contains the name of the object associated with the reported event.|  
|ObjectPath|14|8|Contains the object path for the object associated with the reported event, as a comma-separated list of parents starting with the object's parents.|  
|ObjectReference|15|8|Contains the object reference for the reported event, encoded as XML for all parents and using tags to describe the object.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the reported event.|  
|DatabaseName|28|8|Contains the name of the database in which the reported event occurred.|  
|SessionID|39|8|Contains the session ID associated with the reported event.|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the reported event. The SPID directly corresponds to the session GUID used by XML for Analysis (XMLA).|  
|TextData|42|9|Contains the text data associated with the reported event.|  
|ServerName|43|8|Contains the name of the instance on which the reported event occurred.|  
  
## Progress Report Error–Data Columns  
  
|**Column Name**|**Column Id**|**Column Type**|**Column Description**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Event Class is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class. The following are valid **Sub Class Id**: **Sub Class Name** pairs:<br /><br /> 1: **Process**<br /><br /> 2: **Merge**<br /><br /> 3: **Delete**<br /><br /> 4: **DeleteOldAggregations**<br /><br /> 5: **Rebuild**<br /><br /> 6: **Commit**<br /><br /> 7: **Rollback**<br /><br /> 8: **CreateIndexes**<br /><br /> 9: **CreateTable**<br /><br /> 10: **InsertInto**<br /><br /> 11: **Transaction**<br /><br /> 12: **Initialize**<br /><br /> 13: **Discretize**<br /><br /> 14: **Query**<br /><br /> 15: **CreateView**<br /><br /> 16: **WriteData**<br /><br /> 17: **ReadData**<br /><br /> 18: **GroupData**<br /><br /> 19: **GroupDataRecord**<br /><br /> 20: **BuildIndex**<br /><br /> 21: **Aggregate**<br /><br /> 22: **BuildDecode**<br /><br /> 23: **WriteDecode**<br /><br /> 24: **BuildDMDecode**<br /><br /> 25: **ExecuteSQL**<br /><br /> 26: **ExecuteModifiedSQL**<br /><br /> 27: **Connecting**<br /><br /> 28: **BuildAggsAndIndexes**<br /><br /> 29: **MergeAggsOnDisk**<br /><br /> 30: **BuildIndexForRigidAggs**<br /><br /> 31: **BuildIndexForFlexibleAggs**<br /><br /> 32: **WriteAggsAndIndexes**<br /><br /> 33: **WriteSegment**<br /><br /> 34: **DataMiningProgress**<br /><br /> 35: **ReadBufferFullReport**<br /><br /> 36: **ProactiveCacheConversion**<br /><br /> 37: **Backup**<br /><br /> 38: **Restore**<br /><br /> 39: **Synchronize**<br /><br /> 40: **Build Processing Schedule**<br /><br /> 41: **Detach**<br /><br /> 42: **Attach**<br /><br /> 43: **Analyze\Encode Data**<br /><br /> 44: **Compress Segment**<br /><br /> 45: **Write Table Column**<br /><br /> 46: **Relationship Build Prepare**<br /><br /> 47: **Build Relationship Segment**<br /><br /> 48: **Load**<br /><br /> 49: **Metadata Load**<br /><br /> 50: **Data Load**<br /><br /> 51: **Post Load**<br /><br /> 52: **Metadata traversal during Backup**<br /><br /> 53: **VertiPaq**<br /><br /> 54: **Hierarchy processing**<br /><br /> 55: **Switching dictionary**<br /><br /> 57: **Tabular transaction commit**<br /><br /> 58: **Sequence point**<br /><br /> 59: **Tabular object processing**<br /><br /> 60: **Saving database**<br /><br /> 61: **Tokenization store processing**<br /><br /> 63: **Check segment indexes**<br /><br /> 64: **Check tabular data structure**<br /><br /> 65: **Check column data for duplicates or null values**|  
|CurrentTime|2|5|Contains the current time of the reported event, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contains the time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|EndTime|4|5|Contains the time at which the event ended. This column is not populated for starting event classes, such as SQL:BatchStarting or SP:Starting. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|Duration|5|2|Contains the elapsed amount of time (in milliseconds) taken by the event.|  
|JobID|7|1|Contains the job ID associated with the reported event.|  
|SessionType|8|8|Contains the session type (the entity causing the event) associated with the reported event. For processing events, values are:<br /><br /> 1= User<br /><br /> 2= Proactive Caching<br /><br /> 3= Lazy processing|  
|ProgressTotal|9|1|Contains the progress total for the reported event.|  
|IntegerData|10|1|Contains the integer data associated with the reported event, such as the current count of the number of rows processed for a processing event.|  
|ObjectID|11|8|Contains the object ID (a string) associated with the reported event.|  
|ObjectType|12|1|Contains the object type.|  
|ObjectName|13|8|Contains the name of the object associated with the reported event.|  
|ObjectPath|14|8|Contains the object path for the object associated with the reported event, as a comma-separated list of parents starting with the object's parents.|  
|ObjectReference|15|8|Contains the object reference for the reported event, encoded as XML for all parents and using tags to describe the object.|  
|Severity|22|1|Contains the severity level of an exception associated the reported event. Values are:<br /><br /> 0 = Success<br /><br /> 1 = Informational<br /><br /> 2 = Warning<br /><br /> 3 = Error|  
|Error|24|1|Contains the error number of a given event.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the reported event.|  
|DatabaseName|28|8|Contains the name of the database in which the reported event occurred.|  
|SessionID|39|8|Contains the session ID associated with the reported event.|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the reported event. The SPID directly corresponds to the session GUID used by XML for Analysis (XMLA).|  
|TextData|42|9|Contains the text data associated with the reported event.|  
|ServerName|43|8|Contains the name of the instance on which the reported event occurred.|  
