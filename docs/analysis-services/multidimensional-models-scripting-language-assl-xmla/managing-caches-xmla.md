---
title: "Managing Caches (XMLA) | Microsoft Docs"
description: Learn how to use the ClearCache command in XML for Analysis (XMLA) to clear the cache of a specified dimension or partition. 
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: xmla
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Managing Caches (XMLA)
  You can use the [ClearCache](../xmla/xml-elements-commands/clearcache-element-xmla.md) command in XML for Analysis (XMLA) to clear the cache of a specified dimension or partition. Clearing the cache forces [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to rebuild the cache for that object.  
  
## Specifying Objects  
 The [Object](../xmla/xml-elements-properties/object-element-xmla.md) property of the **ClearCache** command can contain an object reference only for one of the following objects. An error occurs if an object reference is for an object other than one of following objects:  
  
 Database  
 Clears the cache for all dimensions and partitions contained in the database.  
  
 Dimension  
 Clears the cache for the specified dimension.  
  
 Cube  
 Clears the cache for all partitions contained in the measure groups for the cube.  
  
 Measure group  
 Clears the cache for all partitions contained in the measure group.  
  
 Partition  
 Clears the cache for the specified partition.  
  
## See Also  
 [Developing with XMLA in Analysis Services](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
