---
title: "Discover Server State Events Data Columns | Microsoft Docs"
description: Learn about the data columns for the Discover Server State event category.
ms.date: 07/19/2021
ms.service: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Discover Server State Events Data Columns

  The Discover Server State event category has the following event classes:  
  
|**Event ID**|**Event Name**|**Event Description**|  
|------------------|--------------------|---------------------------|  
|33|Server State Discover Begin|Start of Server State Discover.|  
|34|Server State Discover Data|Contents of the Server State Discover Response.|  
|35|Server State Discover End|End of Server State Discover.|  
  
 The following tables list the data columns for each of these event classes.  
  
## Server State Discover Begin Class—Data Columns  
  
| Column Name | Column Id | Column Type | Column Description |
| ----------- | --------- | ----------- | ------------------ |
|EventClass|0|1|Event Class is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class:<br /><br /> 1: **DISCOVER_CONNECTIONS**<br /><br /> 2: **DISCOVER_SESSIONS**<br /><br /> 3: **DISCOVER_TRANSACTIONS**<br /><br /> 6: **DISCOVER_DB_CONNECTIONS**<br /><br /> 7: **DISCOVER_JOBS**<br /><br /> 8: **DISCOVER_LOCKS**<br /><br /> 12: **DISCOVER_PERFORMANCE_COUNTERS**<br /><br /> 13: **DISCOVER_MEMORYUSAGE**<br /><br /> 14: **DISCOVER_JOB_PROGRESS**<br /><br /> 15: **DISCOVER_MEMORYGRANT**|  
|CurrentTime|2|5|Contains the current time of the server state discover event, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contains the time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the server state discover event.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|  
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Microsoft Entra accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|ClientProcessID|36|1|Contains the process ID of the client application that created the connection to the server.|  
|ApplicationName|37|8|Contains the name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|  
|SessionID|39|8|Contains the session ID associated with the server state discover event.|  
|NTCanonicalUserName|40|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the server state discover event. The SPID directly corresponds to the session GUID used by XMLA.|  
|TextData|42|9|Contains the text data associated with the event.|  
|ServerName|43|8|Contains the name of the instance on which the server state discover event occurred.|  
|RequestProperties|45|9|Contains the properties of the current XMLA request.|  
  
## Server State Discover Data Class—Data Columns  
  
| Column Name | Column Id | Column Type | Column Description |
| ----------- | --------- | ----------- | ------------------ |
|EventClass|0|1|Event Class is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class:<br /><br /> 1: **DISCOVER_CONNECTIONS**<br /><br /> 2: **DISCOVER_SESSIONS**<br /><br /> 3: **DISCOVER_TRANSACTIONS**<br /><br /> 6: **DISCOVER_DB_CONNECTIONS**<br /><br /> 7: **DISCOVER_JOBS**<br /><br /> 8: **DISCOVER_LOCKS**<br /><br /> 12: **DISCOVER_PERFORMANCE_COUNTERS**<br /><br /> 13: **DISCOVER_MEMORYUSAGE**<br /><br /> 14: **DISCOVER_JOB_PROGRESS**<br /><br /> 15: **DISCOVER_MEMORYGRANT**|  
|CurrentTime|2|5|Contains the current time of the server state discover event, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contains the time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the server state discover event.|  
|SessionID|39|8|Contains the session ID associated with the server state discover event.|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the server state discover event. The SPID directly corresponds to the session GUID used by XMLA.|  
|TextData|42|9|Contains the text data associated with server response to the discover request.|  
|ServerName|43|8|Contains the name of the instance on which the server state discover event occurred.|  
  
## Server State Discover End Class—Data Columns  
  
| Column Name | Column Id | Column Type | Column Description |
| ----------- | --------- | ----------- | ------------------ |
|EventClass|0|1|Event Class is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class:<br /><br /> 1: **DISCOVER_CONNECTIONS**<br /><br /> 2: **DISCOVER_SESSIONS**<br /><br /> 3: **DISCOVER_TRANSACTIONS**<br /><br /> 6: **DISCOVER_DB_CONNECTIONS**<br /><br /> 7: **DISCOVER_JOBS**<br /><br /> 8: **DISCOVER_LOCKS**<br /><br /> 12: **DISCOVER_PERFORMANCE_COUNTERS**<br /><br /> 13: **DISCOVER_MEMORYUSAGE**<br /><br /> 14: **DISCOVER_JOB_PROGRESS**<br /><br /> 15: **DISCOVER_MEMORYGRANT**|  
|CurrentTime|2|5|Contains the current time of the server state discover event, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contains the time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|EndTime|4|5|Contains the time at which the event ended. This column is not populated for starting event classes, such as SQL:BatchStarting or SP:Starting. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|Duration|5|2|Contains the amount of time (in milliseconds) taken by the event.|  
|CPUTime|6|2|Contains the amount of CPU time (in milliseconds) used by the server state discover event.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the server state discover event.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|  
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Microsoft Entra accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|ClientProcessID|36|1|Contains the process ID of the client application that initiated the XMLA request.|  
|ApplicationName|37|8|Contains the name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|  
|SessionID|39|8|Contains the Windows domain account associated with the server state discover event.|  
|NTCanonicalUserName|40|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the server state discover event. The SPID directly corresponds to the session GUID used by XMLA.|  
|TextData|42|9|Contains the text data associated with server response to the discover request.|  
|ServerName|43|8|Contains the name of the instance on which the server state discover event occurred.|  
  
  
  
