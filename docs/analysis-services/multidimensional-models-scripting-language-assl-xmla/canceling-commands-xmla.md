---
title: "Canceling Commands (XMLA) | Microsoft Docs"
description: Learn how the Cancel command in XML for Analysis (XMLA) can cancel a command on a session, a session, a connection, a server process, or an associated session or connection.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: xmla
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Canceling Commands (XMLA)
  Depending on the administrative permissions of the user issuing the command, the [Cancel](../xmla/xml-elements-commands/cancel-element-xmla.md) command in XML for Analysis (XMLA) can cancel a command on a session, a session, a connection, a server process, or an associated session or connection.  
  
## Canceling Commands  
 A user can cancel the currently executing command within the context of the current explicit session by sending a **Cancel** command with no specified properties.  
  
> [!NOTE]  
>  A command running in an implicit session cannot be canceled by a user.  
  
### Canceling Batch Commands  
 If a user cancels a **Batch** command, then all remaining commands not yet executed within the **Batch** command are canceled. If the **Batch** command was transactional, any commands that were executed before the **Cancel** command runs are rolled back.  
  
## Canceling Sessions  
 By specifying a session identifier for an explicit session in the [SessionID](../xmla/xml-elements-properties/id-element-xmla.md) property of the **Cancel** command, a database administrator or server administrator can cancel a session, including the currently executing command. A database administrator can only cancel sessions for databases on which he or she has administrative permissions.  
  
 A database administrator can retrieve the active sessions for a specified database by retrieving the DISCOVER_SESSIONS schema rowset. To retrieve the DISCOVER_SESSIONS schema rowset, the database administrator uses the XMLA **Discover** method and specifies the appropriate database identifier for the SESSION_CURRENT_DATABASE restriction column in the [Restrictions](../xmla/xml-elements-properties/restrictions-element-xmla.md) property of the **Discover** method.  
  
## Canceling Connections  
 By specifying a connection identifier in the [ConnectionID](../xmla/xml-elements-properties/connectionid-element-xmla.md) property of the **Cancel** command, a server administrator can cancel all of the sessions associated with a given connection, including all running commands, and cancel the connection.  
  
> [!NOTE]
>  If the instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cannot locate and cancel the sessions associated with a connection, such as when the data pump opens multiple sessions while providing HTTP connectivity, the instance cannot cancel the connection. If this case is encountered during the execution of a **Cancel** command, an error occurs.  
  
 A server administrator can retrieve the active connections for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance by retrieving the DISCOVER_CONNECTIONS schema rowset using the XMLA **Discover** method.  
  
## Canceling Server Processes  
 By specifying a server process identifier (SPID) in the [SPID](../xmla/xml-elements-properties/id-element-xmla.md) property of the **Cancel** command, a server administrator can cancel the commands associated with a given SPID.  
  
## Canceling Associated Sessions and Connections  
 You can set the [CancelAssociated](../xmla/xml-elements-properties/cancelassociated-element-xmla.md) property to true to cancel the connections, sessions, and commands associated with the connection, session, or SPID specified in the **Cancel** command.  
  
## See Also  
 [Discover Method &#40;XMLA&#41;](../xmla/xml-elements-methods-discover.md)   
 [Developing with XMLA in Analysis Services](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
