---
title: "Analysis Management Objects (AMO) | Microsoft Docs"
ms.date: 07/20/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: amo
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Programming with Analysis Management Objects (AMO)

[!INCLUDE[ssasyes-aasyes](../includes/ssasyes-aasyes.md)]

Analysis Management Objects (AMO) is a library of programmatically accessed objects that enables an application to manage an Analysis Services instance.

This section explains AMO concepts, focusing on major objects, how and when to use them, and the way they are interrelated. For more information about specific objects or classes, see:

- [Microsoft.AnalysisServices Namespace](https://msdn.microsoft.com/library/microsoft.analysisservices.aspx), for reference documentation.
- [Analysis Services Management Objects (AMO)](https://www.bing.com/search?q=Analysis+Services+Management+Objects+%28AMO%29), as a Bing.com general search.

Beginning in SQL Server 2016, AMO is refactored into multiple assemblies. Generic classes such as Server, Database, and Roles are in the **Microsoft.AnalysisServices.Core** Namespace. Multidimensional-specific APIs remain in [Microsoft.AnalysisServices Namespace](https://msdn.microsoft.com/library/ms146720.aspx). 

If you are programming for tabular models at 1200 or higher compatibility level, use the Tabular Object Model (TOM). TOM is an extension of the Analysis Services Management Object (AMO) client library.

Custom scripts and applications written against earlier versions of AMO will continue to work with no modification. However, if you have script or applications that target SQL Server 2016 or later specifically, or if you need to rebuild a custom solution, be sure to add the new assembly and namespace to your project.
