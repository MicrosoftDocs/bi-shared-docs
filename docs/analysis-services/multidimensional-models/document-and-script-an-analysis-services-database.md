---
title: "Document and Script an Analysis Services Database | Microsoft Docs"
description: Use SQL Server Management Studio to output the metadata of the database, or of an object contained in the database, as an XML for Analysis (XMLA) script.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Document and Script an Analysis Services Database
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  After an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to output the metadata of the database, or of an object contained in the database, as an XML for Analysis (XMLA) script. You can output this script to a new **XMLA Query Editor** window, to a file, or to the Clipboard. For more information about XMLA, see [Analysis Services Scripting Language &#40;ASSL for XMLA&#41;](../assl/analysis-services-scripting-language-assl-for-xmla.md).  
  
 The generated XMLA script uses [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL) elements to define the objects contained by the script. If you generated a CREATE script, the resulting XMLA script contains an XMLA **Create** command and ASSL elements that can be used to create the entire [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database structure on an instance. If you generated an ALTER script, the resulting XMLA script contains an XMLA **Alter** command and ASSL elements that can be used to restore the structure of an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to the state of the database at the time the script was created.  
  
 You can use the generated XMLA script from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database in many ways, including:  
  
-   To maintain a backup script that allows you to recreate all the database objects and permissions.  
  
-   To create or update database development code.  
  
-   To create a test or development environment from an existing schema.  
  
## See Also  
 [Modify or Delete an Analysis Services Database](../../analysis-services/multidimensional-models/modify-or-delete-an-analysis-services-database.md)   
 [Alter Element &#40;XMLA&#41;](../xmla/xml-elements-commands/alter-element-xmla.md)   
 [Create Element &#40;XMLA&#41;](../xmla/xml-elements-commands/create-element-xmla.md)  
  
