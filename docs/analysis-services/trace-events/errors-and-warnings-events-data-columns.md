---
title: "Errors and Warnings Events Data Columns | Microsoft Docs"
description: Learn about the data columns for the Security Audit event category.
ms.date: 07/19/2021
ms.prod: sql
ms.technology: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Errors and Warnings Events Data Columns

  The Security Audit event category has the following event class:  
  
-   Error class  
  
 The following table lists the data columns for this event class.  
  
## Error Event Class—Data Columns  
  
|**Column Name**|**Column Id**|**Column Type**|**Column Description**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Event Class is used to categorize events.|  
|StartTime|3|5|Contains the time at which the event started, when available. For filtering, expected formats are 'YYYY-MM-DD' and 'YYYY-MM-DD HH:MM:SS'.|  
|SessionType|8|8|Contains the type of the entity that caused the error.|  
|Severity|22|1|Contains the severity level of an exception associated with the error event. Values are:<br /><br /> 0 = Success<br /><br /> 1 = Informational<br /><br /> 2 = Warning<br /><br /> 3 = Error|  
|Success|23|1|Contains the success or failure of the error event. Values are:<br /><br /> 0 = Failure<br /><br /> 1 = Success|  
|Error|24|1|Contains the error number of any error associated with the error event.|  
|ConnectionID|25|1|Contains the unique connection ID associated with the error event.|  
|DatabaseName|28|8|Contains the name of the Analysis Services instance on which the error event occurred.|  
|NTUserName|32|8|Contains the user name associated with the command event. Depending on the environment, the user name is in the following form:</br> - Windows user account (DOMAIN\UserName)</br> - User Principal Name (UPN) (username@domain.com)</br> - Service  Principal Name (SPN) (appid@tenantid)</br> - Power BI Service Account  (Power BI Service)</br> - Power BI Service on behalf of a UPN or SPN (Power BI Service (UPN/SPN))|  
|NTDomainName|33|8|Contains the domain name associated with the user account that triggered the command event. </br> - Windows domain name for Windows user accounts</br> - AzureAD for Azure Active Directory accounts</br> - NT AUTHORITY accounts without a Windows domain name, such as the Power BI service|  
|ClientHostName|35|8|Contains the name of the computer on which the client is running. This data column is populated if the host name is provided by the client.|  
|ClientProcessID|36|1|Contains the process ID of the client application.|  
|ApplicationName|37|8|Contains the name of the client application that created the connection to the server. This column is populated with the values passed by the application rather than the displayed name of the program.|  
|SessionID|39|8|Contains the server process ID (SPID) that uniquely identifies the user session associated with the error event. The SPID directly corresponds to the session GUID used by XML for Analysis (XMLA).|  
|SPID|41|1|Contains the server process ID (SPID) that uniquely identifies the user session associated with the error event. The SPID directly corresponds to the session GUID used by XML for Analysis (XMLA).|  
|TextData|42|9|Contains the text data associated with the error event.|  
|ServerName|43|8|Contains the name of the server running Analysis Services instance on which the error event occurred.|  

  
  
