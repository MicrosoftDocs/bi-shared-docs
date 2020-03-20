---
title: "Create and deploy an empty database (AMO-TOM) | Microsoft Docs"
ms.date: 07/20/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Create and deploy an empty database (AMO-TOM)

[!INCLUDE[ssas-appliesto-sql2016-later-aas-pbip](../includes/ssas-appliesto-sql2016-later-aas-pbip.md)]

A common programming scenario for AMO-TOM is to generate databases and models on the fly. This article walks you through the steps of creating a database. 

For tabular solutions, there is a one-to-one correspondence between a database and model, with one model per database. You can typically specify one or the other, and the engine will infer the missing object. 

Creating and deploying a new database is a three-part task: 

* Instantiate a **Database** object and set its properties, including a name. 

* Add the **Database** object to a **Server.Databases** collection. 

* Call the **Update** method on the **Database** object to save it to the **Server**. 

## Code example: create empty database 

```csharp
using System; 
using Microsoft.AnalysisServices; 
using Microsoft.AnalysisServices.Tabular; 
 
namespace TOMSamples 
{ 
    class Program 
    { 
        static void Main(string[] args) 
        { 
            // 
            // Connect to the local default instance of Analysis Services 
            // 
            string ConnectionString = "DataSource=localhost"; 
 
            // 
            // The using syntax ensures the correct use of the 
            // Microsoft.AnalysisServices.Tabular.Server object. 
            // 
            using (Server server = new Server()) 
            { 
                server.Connect(ConnectionString); 
 
                // 
                // Generate a new database name and use GetNewName 
                // to ensure the database name is unique. 
                // 
                string newDatabaseName = 
                    server.Databases.GetNewName("New Empty Database"); 
 
                // 
                // Instantiate a new  
                // Microsoft.AnalysisServices.Tabular.Database object. 
                // 
                var blankDatabase = new Database() 
                { 
                    Name = newDatabaseName, 
                    ID = newDatabaseName, 
                    CompatibilityLevel = 1200, 
                    StorageEngineUsed = StorageEngineUsed.TabularMetadata, 
                }; 
                // 
                // Add the new database object to the server's  
                // Databases connection and submit the changes 
                // with full expansion to the server. 
                // 
                server.Databases.Add(blankDatabase); 
                blankDatabase.Update(UpdateOptions.ExpandFull); 

                Console.Write("Database "); 
                Console.ForegroundColor = ConsoleColor.Yellow; 
                Console.Write(blankDatabase.Name); 
                Console.ResetColor(); 
                Console.WriteLine(" created successfully."); 
                Console.WriteLine(); 
            } 
            Console.WriteLine("Press Enter to close this console window."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## Next steps 

Once a database is created, you can add Model objects: 

- [Add a data source to a Tabular model](add-a-data-source-to-tabular-model-analysis-services-amo-tom.md)
- [Create tables, partitions, and columns in a Tabular model](create-tables-partitions-and-columns-in-a-tabular-model.md)
 
