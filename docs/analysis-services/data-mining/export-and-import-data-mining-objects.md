---
title: "Export and Import Data Mining Objects | Microsoft Docs"
description: Learn how to import and export data mining objects in SQL Server Analysis Services by using DMX statements.
ms.date: 10/31/2023
ms.service: azure-analysis-services
ms.custom: data-mining
ms.topic: concept-article

---
# Export and import data mining objects
[!INCLUDE[appliesto-sql2019-earlier](../includes/appliesto-sql2019-earlier.md)]

[!INCLUDE[dm-dep-banner](../includes/dm-dep-banner.md)]

  In addition to the functionality provided in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] for backing up, restoring, and migrating solutions, SQL Server Data Mining provides the ability to quickly transfer data mining structures and models between different servers by using Data Mining Extensions (DMX).  
  
 If your data mining solution uses relational data instead of a multidimensional database, transferring models by using **EXPORT** and **IMPORT** is much faster and easier than either using database restore or deploying an entire solution.  
  
 This section provides an overview of how to transfer data mining structures and models by using DMX statements. For syntax details and examples, see [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx) and [IMPORT &#40;DMX&#41;](/sql/dmx/import-dmx).  
  
> [!NOTE]  
>  You must be a database or server administrator to export or import objects from a Microsoft SQL Server Analysis Services database.  
  
## Exporting data mining structures  
 When you export a mining structure, the EXPORT statement automatically exports all associated models. To control which objects are exported, you must specify each object by name.  
  
 If the mining structure is processed and the results are cached, which is the default behavior, the exported mining structure definition contains a summary of the data the structure is based on. To remove this summary, you must clear the cache associated with the mining structure by performing a **Process Clear Structure** operation. For more information, see [Process a Mining Structure](../../analysis-services/data-mining/process-a-mining-structure.md).  
  
## Exporting data mining models  
 Use the **WITH DEPENDENCIES** keyword to export the data source and data source view definition along with the mining model and its structure.  
  
 When you export a mining model without exporting its dependencies, the EXPORT statement exports the definition of the mining model and its mining structure, but doesn't export the definition of the data sources. Therefore, you can browse the model immediately after you import the model, but to reprocess the mining model on the target server, or run queries against the underlying data, you must create a corresponding data source on the destination server.  
  
## Importing data mining structures and models  
 When you import a data mining object, the object imports to the server and database you're connected to when you execute the IMPORT statement. If the import file includes a database that doesn't exist on the server, the database is created.  
  
 You can also import a mining structure or mining model by using the **Restore** command. Your models or structures restore into the database that has the same name as the database they were exported from. For more information, see [Restore options](../../analysis-services/multidimensional-models/restore-options.md).
  
## Remarks  
 You can't import a model or structure to a server that already has a model or structure with the same name. You also can't rename a data mining object in an export file. To avoid naming conflicts, either delete the original data mining object on the target server or rename the data mining object before you export the definition.  
  
## See also  
 [Management of Data Mining Solutions and Objects](../../analysis-services/data-mining/management-of-data-mining-solutions-and-objects.md)  
  
  
