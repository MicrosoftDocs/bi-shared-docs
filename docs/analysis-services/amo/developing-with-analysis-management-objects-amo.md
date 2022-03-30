---
title: "Analysis Management Objects (AMO) | Microsoft Docs"
description: Learn how Analysis Management Objects (AMO) is a library of programmatically accessed objects that enables an application to manage an Analysis Services instance.
ms.date: 03/30/2022
ms.prod: sql
ms.technology: analysis-services
ms.custom: amo
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || sql-analysis-services-2016 || sql-analysis-services-2017 || sql-analysis-services-2019 || sql-analysis-services-2022"

---
# Analysis Management Objects (AMO)

[!INCLUDE[ssas-appliesto-sqlas-aas](../includes/ssas-appliesto-sqlas-aas.md)]

Analysis Management Objects (AMO) is a library of programmatically accessed objects that enables an application to manage an Analysis Services instance.

If you are programming for Azure Analysis Services, SQL Server Analysis Services, or Power BI Premium tabular models at 1200 or higher compatibility level, use the [Tabular Object Model](../tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo.md) (TOM). TOM is an extension of the Analysis Services Management Object (AMO) client library.

This section explains AMO concepts, focusing on major objects, how and when to use them, and the way they are interrelated. For more information about specific objects or classes, see:

- [Microsoft.AnalysisServices Namespace](/dotnet/api/microsoft.analysisservices), for reference documentation.
- [Analysis Services Management Objects (AMO)](https://www.bing.com/search?q=Analysis+Services+Management+Objects+%28AMO%29), as a Bing.com general search.

Beginning with SQL Server 2016, AMO is refactored into multiple assemblies. Generic classes such as Server, Database, and Roles are in the **Microsoft.AnalysisServices.Core** Namespace. Multidimensional-specific APIs remain in [Microsoft.AnalysisServices Namespace](/dotnet/api/microsoft.analysisservices).

Custom scripts and applications written against earlier versions of AMO will continue to work with no modification. However, if you have script or applications that target SQL Server 2016 or later specifically, or if you need to rebuild a custom solution, be sure to add the new assembly and namespace to your project.
