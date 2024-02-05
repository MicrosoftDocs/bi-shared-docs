---
title: "Disconnect Users and Sessions on Analysis Services Server | Microsoft Docs"
description: Learn how to disconnect users and sessions on SQL Server Analysis Services while they are active.
ms.date: 07/16/2019
ms.service: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || >= sql-analysis-services-2016"
---
# Disconnect users and sessions from Analysis Services

[!INCLUDE[appliesto-sqlas-all-aas](../includes/appliesto-sqlas-all-aas.md)]

  As an administrator, you may want to end user activity as part of workload management. You do this by canceling sessions and connections. Sessions can be formed automatically when a query is run (implicit), or named at the time of creation by the administrator (explicit). Connections to SQL Server Analysis Services are open conduits over which queries can be run. Azure Analysis Services and Power BI workspaces use sessions over HTTP. Both sessions and connections can be ended while they are active. For example, you may want to end processing for a session if the processing is taking too long, or if some doubt has arisen as to whether the command being executed was written correctly.  
  
## Ending Sessions and Connections  
 To manage sessions and connections, use Dynamic Management Views (DMVs) and XMLA:  
  
1.  In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an Analysis Services instance.  
  
2.  Paste any one of the following DMV queries in an MDX query window to get a list of all sessions, connections, and commands that are currently executing:  
  
     `Select * from $System.Discover_Sessions`  
  
     `Select * from $System.Discover_Connections`  (This query does not apply to Azure Analysis Services)
  
     `Select * from $System.Discover_Commands`  
  
3.  Press F5 to execute the query.  
  
     The DMV query returns session and connection information in a tabular result set that is easier read and copy from.  
  
 Keep the query window open. In the next step, you will want to return to this page to copy the SPIDs of the session you want to disconnect.  
  
 To end a session, open a second XMLA query window.  
  
1.  Paste the following syntax into an MDX query window, replacing the ConnectionID, SessionID, or SPID placeholder with a valid value copied from the previous step.  
  
    ```  
    <Cancel xmlns="http://schemas.microsoft.com/analysisservices/2003/engine">  
  
       <ConnectionID>111</ConnectionID>  
       <SessionID>222</SessionID>  
       <SPID>333</SPID>  
  
    <CancelAssociated>1</CancelAssociated>  
    </Cancel>  
  
    ```  
  
2.  Press F5 to execute the cancel command.  

Canceling a SPID/SessionID will cancel any active commands running on the session corresponding to the SPID/SessionID. Canceling a connection will identify the session associated with the connection, and cancel any active commands running on that session. In rare cases, a connection is not closed if the engine cannot track all sessions and SPIDs associated with the connection; for example, when multiple sessions are open in an HTTP scenario.   
  
To learn more about the XMLA referenced in this topic, see [Execute Method &#40;XMLA&#41;](../xmla/xml-elements-methods-execute.md) and [Cancel Element &#40;XMLA&#41;](../xmla/xml-elements-commands/cancel-element-xmla.md).  
  
## See also  

 [Managing Connections and Sessions &#40;XMLA&#41;](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md)   
 [BeginSession Element &#40;XMLA&#41;](../xmla/xml-elements-headers/beginsession-element-xmla.md)   
 [EndSession Element &#40;XMLA&#41;](../xmla/xml-elements-headers/endsession-element-xmla.md)   
 [Session Element &#40;XMLA&#41;](../xmla/xml-elements-headers/session-element-xmla.md)