---
title: "Session Events Data Columns | Microsoft Docs"
description: Learn about the data columns for the Session Events event category.
ms.date: 07/19/2021
ms.service: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Session Events Data Columns

  The Session Events event category has the following event class:  
  
|**Event ID**|**Event Name**|**Event Description**|  
|------------------|--------------------|---------------------------|  
|41|Existing Connection|Existing user connection.|  
|42|Existing Session|Existing session.|  
|43|Session Initialize|Session Initialize.|  
  
 The following table lists the data columns for this event class.  
  
## Existing Connection  
  
|**Column Name**|**Column Id**|**Column Type**|**Column Description**|  
|---------------------|-------------------|---------------------|----------------------------|  
|CurrentTime|2|5|Time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|ConnectionID|25|1|Unique connection ID.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Microsoft Entra accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|ClientHostName|35|8|Name of the computer on which the client is running. This data column is populated if the host name is provided by the client.|  
|ClientProcessID|36|1|The process ID of the client application.|  
|ApplicationName|37|8|Name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|  
|SPID|41|1|Server process ID. This uniquely identifies a user session. This directly corresponds to the session GUID used by XML/A.|  
|ServerName|43|8|Name of the server producing the event.|  
  
## Existing Session  
  
|**Column Name**|**Column Id**|**Column Type**|**Column Description**|  
|---------------------|-------------------|---------------------|----------------------------|  
|CurrentTime|2|5|Time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|Duration|5|2|Amount of time (in milliseconds) taken by the event.|  
|CPUTime|6|2|Amount of CPU time (in milliseconds) used by the event.|  
|ConnectionID|25|1|Unique connection ID.|  
|DatabaseName|28|8|Name of the database in which the statement of the user is running.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))| 
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Microsoft Entra accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|ClientHostName|35|8|Name of the computer on which the client is running. This data column is populated if the host name is provided by the client.|  
|ClientProcessID|36|1|The process ID of the client application.|  
|ApplicationName|37|8|Name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|  
|NTCanonicalUserName|40|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|  
|SPID|41|1|Server process ID. This uniquely identifies a user session. This directly corresponds to the session GUID used by XML/A.|  
|TextData|42|9|Text data associated with the event.|  
|ServerName|43|8|Name of the server producing the event.|  
|RequestProperties|45|9|XMLA request properties.|  
  
## Session Initialize  
  
| Column Name | Column Id | Column Type | Column Description |
| ----------- | --------- | ----------- | ------------------ |
|CurrentTime|2|5|Time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|ConnectionID|25|1|Unique connection ID.|  
|DatabaseName|28|8|Name of the database in which the statement of the user is running.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))| 
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Microsoft Entra accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|ClientHostName|35|8|Name of the computer on which the client is running. This data column is populated if the host name is provided by the client.|  
|ClientProcessID|36|1|The process ID of the client application.|  
|ApplicationName|37|8|Name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|  
|NTCanonicalUserName|40|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|  
|SPID|41|1|Server process ID. This uniquely identifies a user session. This directly corresponds to the session GUID used by XML/A.|  
|TextData|42|9|Text data associated with the event.|  
|ServerName|43|8|Name of the server producing the event.|  
|RequestProperties|45|9|XMLA request properties.|  
