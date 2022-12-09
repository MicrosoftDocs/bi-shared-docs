---
title: "Queries Events Data Columns | Microsoft Docs"
description: Learn about the data columns for the Queries Events event category.
ms.date: 07/19/2021
ms.service: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Queries Events Data Columns

  The Queries Events event category has the following event classes:  
  
|**Event ID**|**Event Name**|**Event Description**|  
|------------------|--------------------|---------------------------|  
|9|Query Begin|Query begin.|  
|10|Query End|Query end.|  
  
 The following tables list the data columns for each of these event classes.  
  
## Query Begin Class—Data Columns  
  
|**Column Name**|**Column Id**|**Column Type**|**Column Description**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Event Class is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class.<br /><br /> 0: MDXQuery<br /><br /> 1: DMXQuery<br /><br /> 2: SQLQuery<br /><br /> 3: DAXQuery|  
|CurrentTime|2|5|Contains the current time of the event, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contains the time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the query event.|  
|DatabaseName|28|8|Contains the name of the database in which the query is running.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|  
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Azure Active Directory accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|ClientProcessID|36|1|Contains the process ID of the client application.|  
|ApplicationName|37|8|Contains the name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|  
|SessionID|39|8|Contains the session unique ID of the XMLA request.|  
|NTCanonicalUserName|40|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the query event. The SPID directly corresponds to the session GUID used by XMLA.|  
|TextData|42|9|Contains the text data associated with the query event.|  
|ServerName|43|8|Contains the name of the instance on which the query event occurred.|  
|RequestParameters|44|9|Contains the parameters for parameterized queries and commands associated with the query event.|  
|RequestProperties|45|9|Contains the properties of the XMLA request.|  
  
## Query End Class—Data Columns  
  
|**Column Name**|**Column Id**|**Column Type**|**Column Description**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Event Class is used to categorize events.|  
|EventSubclass|1|1|Event Subclass provides additional information about each event class.<br /><br /> 0: MDXQuery<br /><br /> 1: DMXQuery<br /><br /> 2: SQLQuery<br /><br /> 3: DAXQuery|  
|CurrentTime|2|5|Contains the current time of the event, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contains the time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|EndTime|4|5|Contains the time at which the event ended. This column is not populated for starting event classes, such as SQL:BatchStarting or SP:Starting. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|Duration|5|2|Contains the amount of elapsed time (in milliseconds) taken by the event.|  
|CPUTime|6|2|Contains the amount of CPU time (in milliseconds) used by the event.|  
|Severity|22|1|Contains the severity level of an exception associated with the query event. Values are:<br /><br /> 0 = Success<br /><br /> 1 = Informational<br /><br /> 2 = Warning<br /><br /> 3 = Error|  
|Success|23|1|Contains the success or failure of the query event. Values are:<br /><br /> 0 = Failure<br /><br /> 1 = Success|  
|Error|24|1|Contains the error number of any error associated with the query event.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the query event.|  
|DatabaseName|28|8|Contains the name of the database in which the query is running.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|  
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Azure Active Directory accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|ClientProcessID|36|1|Contains the process ID of the client application.|  
|ApplicationName|37|8|Contains the name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|  
|SessionID|39|8|Contains the session unique ID of the XMLA request.|  
|NTCanonicalUserName|40|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account (Power BI Service)|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the query event. The SPID directly corresponds to the session GUID used by XMLA.|  
|TextData|42|9|Contains the text data associated with the query event.|  
|ServerName|43|8|Contains the name of the instance on which the query event occurred.|  
