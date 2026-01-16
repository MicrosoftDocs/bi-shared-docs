---
title: "Analysis Services developer documentation | Microsoft Docs"
description: Learn about the contents of Analysis Services developer documentation, including writing managed code and using open standards like XMLA and MSOLAP.
ms.date: 04/07/2021
ms.service: analysis-services
ms.custom:
ms.topic: concept-article
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Analysis Services developer documentation

[!INCLUDE[appliesto-sqlas-all-aas-pbip](includes/appliesto-sqlas-all-aas-pbip.md)]

With Analysis Services, almost every object and workload is programmable, and often there is more than one approach to choose from.  Options include writing managed code, script, or using open standards like XMLA and MSOLAP if your solution requirements preclude using the .NET framework.

## What you can accomplish in code

Typical programming scenarios include server, database, and semantic model deployment, administration, data refresh and partition management, data access from custom applications, and external tools. Common to all these scenarios is a fixed architecture and object definition hierarchy, with well-understood operations that span data definition, processing, and query workloads.

Although objects and workloads are programmable, they're not extensible. Specifically, you cannot create custom data cartridges that retrieve data from unsupported data sources, customize or replace formula or storage engine behaviors, nor can you create new types of object metadata on a server, database, or model.

To further elaborate on the last point about creating new object types, while you can't create a new type of object, you can create calculated objects built from expressions or code at run time. Not everything in your model needs to be predefined and mapped to an existing data structure. Additionally, you can extend the schema via Annotations in AMO to pass object-specific information to your client application.

## Choose a platform or approach to development

Analysis Services provides many ways to customize a solution through code, but most developers use the managed APIs or script.

- Managed APIs include [AMO](amo/developing-with-analysis-management-objects-amo.md) and [TOM](tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo.md) for data definition and administrative tasks, and [ADOMD.NET](adomd/developing-with-adomd-net.md) for query support from client code. In SQL Server 2016 and later, AMO is updated to use the new Tabular metadata for models created or upgraded to compatibility level 1200 and higher.

- Script can often achieve the same results as a program executable, with possibly less work.

  - You can write PowerShell script using Analysis Services PowerShell components that call AMO types directly. Within PowerShell, you can also create and execute ASSL/XMLA or TMSL (in JSON) script.

  - [TMSL](tmsl/tabular-model-scripting-language-tmsl-reference.md) and [ASSL](assl/analysis-services-scripting-language-assl-for-xmla.md) are script languages that provide  objects used in discover and execute operations. Which type of script you use depends on the underlying server, database, or model.

  - Tabular models or databases at compatibility level 1200 and higher use the Tabular Model Scripting Language (TMSL), which is in JSON.

  - Multidimensional models and Tabular models at compatibility levels 1050-1103 use Analysis Services Scripting Language (ASSL), which is the Analysis Services extension of the XMLA open standard.

  - You can generate ASSL or TMSL script in Management Studio. You can also use **View Code** in SQL Server Data Tools to view the model definition in ASSL or TMSL.

- While it's possible to build a solution based on the open standards of XMLA and MDX, it's quite rare to do so. There is no documentation other than XMLA and MDX reference to help you, and most community and forum support draws from experiences with .NET or native (MSOLAP) technologies.

## Programming for Analysis Services

[Analysis Services Management Objects (AMO)](amo/developing-with-analysis-management-objects-amo.md) - Developer reference documentation for the managed provider, Analysis Services Management Objects (AMO), for data definition and administration, including processing.

[Tabular Object Model](tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo.md) - An extension of the AMO client library, created to support programming scenarios for tabular models created at compatibility level 1200 and higher.

[Tabular Model Definition Language (TMDL)](tmdl/tmdl-overview.md) - An object model definition syntax for tabular data models at compatibility level 1200 or higher. Fully compatible with TOM. Text-based and optimized for human interaction and readability.

[Tabular Model Scripting Language (TMSL) Reference](tmsl/tabular-model-scripting-language-tmsl-reference.md) - A JSON representation of Tabular models at compatibility level 1200 and higher. Object definitions are based on tabular metadata constructs like table, column, and relationship rather than multidimensional metadata that might be unfamiliar if you are new to Analysis Services data modeling in Tabular mode.

[Multidimensional model programming](../analysis-services/multidimensional-models/multidimensional-model-programming.md) - Describes the development tasks and approaches for integrating multidimensional model objects in a custom solution.

[ADOMD.NET](adomd/developing-with-adomd-net.md) - Developer reference documentation for the managed provider, ADOMD.NET, used for programmatic data access and query workloads.

[XML for Analysis  &#40;XMLA&#41; reference](xmla/xml-for-analysis-xmla-reference.md) - 
Describes XMLA concepts that can help you understand how XMLA contributes to your custom solution. It also describes the level of compliance with the XMLA 1.1 specification.

[Analysis Services Scripting Language &#40;ASSL for XMLA&#41;](assl/analysis-services-scripting-language-assl-for-xmla.md) - Describes the ASSL extensions to XMLA. ASSL provides a data definition and manipulation language for Analysis Services multidimensional models that supplements the XMLA specification.

[Analysis Services Schema Rowsets](instances/analysis-services-schema-rowsets.md) - Describes the schema rowsets that provide information about server state, server operations, and database objects.

[Analysis Services PowerShell reference](../analysis-services/powershell/analysis-services-powershell-reference.md) - Documents the cmdlets used for administrative functions, plus the general-purpose **Invoke-ASCmd** cmdlet that accepts any script or query as input.
