---
title: "Developing with Analysis Services Scripting Language (ASSL) | Microsoft Docs"
description: Learn how you can use ASSL in custom applications to communicate with Analysis Services over the XMLA protocol.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: xmla
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Developing with Analysis Services Scripting Language (ASSL)
[!INCLUDE[appliesto-sqlas](../../includes/appliesto-sqlas.md)]
  Analysis Services Scripting Language (ASSL) is an extension to XMLA that adds an object definition language and command language for creating and managing Analysis Services structures directly on the server. You can use ASSL in custom application to communicate with Analysis Services over the XMLA protocol. ASSL is made up of two parts:  
  
-   A Data Definition Language (DDL), or object definition language, defines and describes an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], as well as the databases and database objects that the instance contains.  
  
-   A command language that sends action commands, such as **Create**, **Alter**, or **Process**, to an instance of Analysis Services. This command language is discussed in the [XML for Analysis  &#40;XMLA&#41; Reference](../../xmla/xml-for-analysis-xmla-reference.md).  
  
 To view the ASSL that describes a multidimensional solution in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can use the View Code command at the project level. You can also create or edit ASSL script in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] using the XMLA query editor. The scripts you build can be used to manage objects or run commands on the server.  
  
## See Also  
 [ASSL Objects and Object Characteristics](../../../analysis-services/multidimensional-models/scripting-language-assl/assl-objects-and-object-characteristics.md)   
 [ASSL XML Conventions](../../../analysis-services/multidimensional-models/scripting-language-assl/assl-xml-conventions.md)   
 [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md)  
  
