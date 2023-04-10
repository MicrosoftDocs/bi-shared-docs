---
title: "Analysis Services tabular model programming for compatibility level 1200 | Microsoft Docs"
description: Learn how tabular metadata is used to describe model constructs beginning with compatibility level 1200.
ms.date: 04/03/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Tabular model programming for compatibility level 1200 and higher

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Beginning with compatibility level 1200, tabular metadata is used to describe model constructs, replacing historical multidimensional metadata as descriptors for tabular model objects. Metadata for tables, columns, and relationships are table, column, and relationship, rather than the multidimensional equivalents (dimension and attribute).  

> [!IMPORTANT]
> Power BI Premium supports tabular models at the 1500 and higher compatibility level.
  
You can create new models at compatibility level 1200 or higher by using the Microsoft.AnalysisServices.Tabular APIs, the latest version of Visual Studio with Analysis Services projects, or by changing the **CompatibilityLevel** of an existing tabular model to upgrade it (also done in Visual Studio). Doing so binds the model to newer versions of the server, tools, and programming interfaces.
  
Upgrading an existing tabular solution is recommended but not required. Existing script and custom solutions that access or manage tabular models or databases can be used as-is. Azure Analysis Services supports compatibility level 1200 and higher only.
  
New tabular models require different code and script, summarized below.  
  
## Object model definitions as tabular metadata constructs

The Tabular Object Model for 1200 or higher models is exposed in JSON through the [Tabular Model Scripting Language](../tmsl/tabular-model-scripting-language-tmsl-reference.md) and through the AMO data definition language through a new namespace, [Microsoft.AnalysisServices.Tabular](/dotnet/api/microsoft.analysisservices.tabular)

The [Tabular Model Definition Language (TMDL)](../tmdl/tmdl-overview.md) is text-based object model definition syntax for tabular data models at compatibility level 1200 or higher. It is fully compatible with the TOM.

## Script for tabular models and databases

 TMSL is a JSON scripting language for tabular models, with support for create, read, update, an delete operations. You can refresh data via TMSL and invoke database operations for attach, detach, backup, restore, and synchronize. AMO PowerShell accepts TMSL script as input.  
  
 See [Tabular Model Scripting Language &#40;TMSL&#41; Reference](../tmsl/tabular-model-scripting-language-tmsl-reference.md) and [Analysis Services PowerShell Reference](../../analysis-services/powershell/analysis-services-powershell-reference.md) for more information.  
  
## Query languages

 DAX and MDX are supported for all tabular models.  
  
## Expression language

 Filters and expressions used to create calculated objects, including measures and KPIs, are formulated in DAX. See [DAX in tabular models](../../analysis-services/tabular-models/understanding-dax-in-tabular-models-ssas-tabular.md).  
  
## Managed code for tabular models and databases

 AMO includes a new namespace, Microsoft.AnalysisServices.Tabular, for working with models programmatically. See [Microsoft.AnalysisServices.Tabular Namespace](/dotnet/api/microsoft.analysisservices.tabular) for more information.  
  
## See also

 [Analysis Services developer documentation](../../analysis-services/analysis-services-developer-documentation.md)  
 [Technical reference](../../analysis-services/powershell/analysis-services-powershell-reference.md)  
 [Compatibility levels of tabular models and databases](../../analysis-services/tabular-models/tabular-model-programming-for-compatibility-levels-1050-through-1103.md)  
