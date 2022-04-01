---
title: "Analysis Services lock manager properties | Microsoft Docs"
description: Learn about the available lock manager properties in Analysis Services, like DefaultLockTimeoutMS and DeadlockDetectionGranularityMS.
ms.date: 05/03/2021
ms.prod: sql
ms.technology: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || >= sql-analysis-services-2016"
---
# Lock manager properties

[!INCLUDE[appliesto-sqlas-all-aas](../includes/appliesto-sqlas-all-aas.md)]

[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] supports the following lock manager server properties.  
  
 **Applies to:** Multidimensional and tabular server mode  
  
## Properties

 **DefaultLockTimeoutMS**  
 A signed 32-bit integer property that defines default lock timeout in milliseconds for internal lock requests.  
  
 The default value for this property is -1, which indicates there is no timeout for internal lock requests.  
  
 **LockWaitGranularityMS**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
 **DeadlockDetectionGranularityMS**  
 An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../includes/msconame-md.md)] support.  
  
## See also

 [Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md)   
 [Determine the Server Mode of an Analysis Services Instance](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
