---
title: "Proactive Caching (Dimensions) | Microsoft Docs"
description: Learn how proactive caching provides automatic MOLAP cache creation and management for OLAP objects. 
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: olap
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Proactive Caching (Dimensions)
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  Proactive caching provides automatic MOLAP cache creation and management for OLAP objects. The cubes immediately incorporate changes that are made to the data in the database, based upon notifications received from the database. The goal of proactive caching is to provide the performance of traditional MOLAP, while retaining the immediacy and ease of management offered by ROLAP.  
  
 A simple <xref:Microsoft.AnalysisServices.ProactiveCaching> object is composed of: timing specification, and table notification. The timing specification defines the timeframe for updating the cache after a change notification has been received. The table notification defines the notification schema between the data table and the <xref:Microsoft.AnalysisServices.ProactiveCaching> object.  
  
  
