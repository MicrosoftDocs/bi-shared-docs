---
title: "Analysis Services network properties | Microsoft Docs"
description: Learn about the available network properties in Analysis Services, like ListenOnlyOnLocalConnections and MaxAllowedRequestSize.
ms.date: 07/21/2022
ms.service: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"
---

# Network properties

[!INCLUDE[appliesto-sqlas-all-aas](../includes/appliesto-sqlas-all-aas.md)]

Analysis Services supports the following network properties.
  
## General

##### ListenOnlyOnLocalConnections

A Boolean property that identifies whether to listen only on local connections, for example localhost.  
  
## Listener

##### IPV4Support

A signed 32-bit integer property that defines support for IPv4 protocol. This property has one of the values listed in the following table:  
  
|Value|Description|  
|-----------|-----------------|  
|*0*|IPv4 disabled; clients can't connect.|  
|*1*|(Default) IPv4 is required; server won't start if it cannot listen to IPv4.|  
|*2*|IPv4 is optional; server tries to listen to IPv4 but starts even if unable to.|  
  
##### IPV6Support

A signed 32-bit integer property that defines support for IPv6 protocol. This property has one of the values listed in the following table:  
  
|Value|Description|  
|-----------|-----------------|  
|*0*|IPv6 disabled; clients can't connect.|  
|*1*|(Default) IPv6 is required; server won't start if it cannot listen to IPv6.|  
|*2*|IPv6 is optional; server tries to listen to IPv6 but starts even if unable to.|  
  
##### MaxAllowedRequestSize

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### RequestSizeThreshold

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### ServerReceiveTimeout

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### ServerSendTimeout

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
## Requests

##### EnableBinaryXML

A Boolean property that specifies whether the server will recognize requests binary xml format.  
  
##### EnableCompression

A Boolean property that specifies whether compression is enabled for requests.  
  
## Responses

##### CompressionLevel

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### EnableBinaryXML

A Boolean property that specifies whether the server is enabled for binary xml responses.  
  
##### EnableCompression

A Boolean property that specifies whether compression is enabled for responses to client requests.  
  
## TCP

##### InitialConnectTimeout

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MaxCompletedReceiveCount

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MaxPendingAcceptExCount

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MaxPendingReceiveCount

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MaxPendingSendCount

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MinPendingAcceptExCount

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### MinPendingReceiveCount

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### ScatterReceiveMultiplier

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### SocketOptions\ DisableNonblockingMode

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### SocketOptions\ EnableLingerOnClose

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### SocketOptions\EnableNagleAlgorithm

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### SocketOptions\ LingerTimeout

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### SocketOptions\ ReceiveBufferSize

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
##### SocketOptions\ SendBufferSize

An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
## See also

[Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md)   
[Determine the Server Mode of an Analysis Services Instance](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
