---
title: "Translations in Analysis Services | Microsoft Docs"
description: Learn how Analysis Services supports translations to provide culture-specific strings based on the locale identifier (LCID).
ms.date: 01/05/2021
ms.prod: sql
ms.technology: analysis-services
ms.custom:
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Translations in Analysis Services

[!INCLUDE[ssas-appliesto-sqlas-all-aas-pbip](includes/ssas-appliesto-sqlas-all-aas-pbip.md)]

In [!INCLUDE[ssASnoversion](includes/ssasnoversion-md.md)] data models, you can embed multiple translations of a caption or description to provide culture-specific strings based on the locale identifier (LCID). For multidimensional models, translations can be added for the database name, cube objects, and database dimension objects. For tabular models, you can translate table and column captions and descriptions.  
  
Defining a translation creates the metadata and translated caption inside the model, but to render localized strings in a client application, you must either set the **Language** property on the object, or pass a **Culture** or **Locale Identifier** parameter on the connection string (for example, by setting `LocaleIdentifier=1036` to return French strings).  
  
Plan on using **Locale Identifier** if you want to support multiple, simultaneous translations of the same object in different languages. Setting the **Language** property works, but it also impacts processing and queries, which could have unintended consequences. Setting **Locale Identifier** is the better choice because it's only used to return translated strings.  
  
A translation consists of a locale identifier (LCID), a translated caption for the object (for example, the dimension or attribute name), and optionally, a binding to a column that provides data values in the target language. You can have multiple translations, but you can only use one for any given connection. There is no theoretical limit on the number of translations you can embed in model, but each translation adds complexity to testing, and all translations must share the same collation, so when designing your solution keep these natural constraints in mind.  
  
> [!TIP]  
> You can use client applications such as Excel, SQL Server Management Studio, and SQL Server Profiler to return translated strings. See [Globalization tips and best practices;](../analysis-services/globalization-tips-and-best-practices-analysis-services.md) for details.  
  
## Add translated metadata

 Visit these links for step-by-step instructions:  
  
- [Translations in Tabular models](../analysis-services/tabular-models/translations-in-tabular-models-analysis-services.md)  
  
- [Translations in Multidimensional models](../analysis-services/multidimensional-models/translations-in-multidimensional-models-analysis-services.md)  
  
## See also

 [Globalization scenarios for Analysis Services](../analysis-services/globalization-scenarios-for-analysis-services.md)  
 [Languages and collations](../analysis-services/languages-and-collations-analysis-services.md)  
 [Set or change the column collation](/sql/relational-databases/collations/set-or-change-the-column-collation)  
 [Globalization tips and best practices](../analysis-services/globalization-tips-and-best-practices-analysis-services.md)  
