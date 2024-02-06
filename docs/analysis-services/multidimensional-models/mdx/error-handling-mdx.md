---
title: "Error Handling (MDX) | Microsoft Docs"
description: Learn how each cube can control how errors within a Multidimensional Expressions (MDX) script are handled.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: mdx
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Error Handling (MDX)
[!INCLUDE[appliesto-sqlas](../../includes/appliesto-sqlas.md)]
  Each cube can control how errors within a Multidimensional Expressions (MDX) script are handled. Error handling is done through the **ScriptErrorHandlingMode** enumerator. The possible values for this enumerator are:  
  
 **IgnoreNone**  
 Causes the server to raise an error when [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] finds any error in the MDX script.  
  
 **IgnoreAll**  
 Causes the server to ignore all commands in the MDX script that contain an error, including syntax errors, name resolution errors, and more.  
  
## See Also  
 <xref:Microsoft.AnalysisServices.Cube.ScriptErrorHandlingMode%2A>  
  
  
