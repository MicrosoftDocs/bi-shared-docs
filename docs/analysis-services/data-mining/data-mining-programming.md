---
title: "Analysis Services Data Mining Programming | Microsoft Docs"
description: Learn about your options create your own extensions for data mining in SQL Server Analysis Services.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: concept-article

---
# Data Mining Programming
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  If you find that the built-in tools and viewers in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] by coding your own extensions. In this approach, you have two options:  
  
-   **XMLA**  
  
     [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] supports XML for Analysis (XMLA) as a protocol for communication with client applications. Additional commands are supported by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that extend the XML for Analysis specification.  
  
     Because [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses XMLA for data definition, data manipulation, and data control support, you can create mining structures and mining models by using the visual tools provided by [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], and then extend the data mining objects that you have created by using Data Mining Extensions (DMX) and Analysis Services Scripting Language (ASSL) scripts.  
  
     You can create and modify data mining objects entirely in XMLA scripts, and run prediction queries against the models programmatically from your own applications.  
  
-   **Analysis Management Objects (AMO)**  
  
     [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] also provides a complete framework that enables third-party data mining providers to integrate the data mining objects into [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].  
  
     You can create mining structures and mining models by using AMO. See the following samples in CodePlex:  
  
    -   AMO Browser  
  
         Connects to the SSAS instance you specify and lists all server objects and their properties, including mining structure and mining models.  
  
    -   AMO Simple Sample  
  
         The AS Simple Sample covers programmatic access to most major objects, and demonstrates metadata browsing, and access to the values in objects.  
  
         The sample also demonstrates how to create and process a data mining structure and model, as well as browse an existing data mining model.  
  
-   **DMX**  
  
     You can use DMX to encapsulate command statements, prediction queries, and metadata queries and return results in a tabular format, assuming you have created a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.  
  
## In This Section  
 [OLE DB for Data Mining](data-mining-programming-ole-db.md)  
 Describes additions to the specification to support data mining and multidimensional data: new schema rowsets and columns, Data Mining Extensions (DMX) language for creating and managing mining structures.  
  
## Related Reference  
 [Developing with ADOMD.NET](../adomd/developing-with-adomd-net.md)  
 Introduces ADOMD.NET client and server programming objects.  
  
 [Developing with Analysis Management Objects &#40;AMO&#41;](../amo/developing-with-analysis-management-objects-amo.md)  
 Introduces the AMO programming library.  
  
 [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../assl/analysis-services-scripting-language-assl-for-xmla.md)  
 Introduces XML for Analysis (XMLA) and its extensions.  
  
## See Also  
 [Analysis Services Developer Documentation](../analysis-services-developer-documentation.md)   
 [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
