---
title: "List existing databases on a tabular server (AMO-TOM) | Microsoft Docs"
description: Learn how to iterate over the Server.Databases collection to list all databases hosted by a server instance.
ms.date: 12/07/2020
ms.service: analysis-services
ms.topic: reference
ms.custom:
  - tabular-models
  - sfi-ropc-nochange

---
# List existing databases on a tabular server (AMO-TOM)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

When you have a **Server** object that is connected to a server instance, you can iterate over **Server.Databases** collection to list all databases hosted by the instance. 

The **Server.Databases** collection contains one **Database** object for every database hosted on the server, regardless of server mode. 

You can check the type of database through **Database.StorageEngineUsed** property.  

Tabular 1200 and higher databases will return a non-null **Database.Model** property that gives access to all tabular metadata objects: Tables, Columns, Relationships, and so on.  

For multidimensional or tabular 1103 and below, the Database.Model property will be null. In this case, non-tabular metadata will be available under multidimensional properties (such as Database.Cubes and Database.Dimensions), but those properties are only exposed by Microsoft.AnalysisServices.Database class (from AMO), not by Microsoft.AnalysisServices.Tabular.Database (for TOM). For more information about which Database class to use, see [Install, distribute, and reference the TOM client library](install-distribute-and-reference-the-tabular-object-model.md).

Unless Database.StorageEngineUsed is set to TabularMetadata, you won't be able to use other classes in the tabular namespace to access or manipulate the model tree. 

The following table summarizes expected behaviors when you connect to a server or database using a Microsoft.AnalysisServices.Tabular class on a server or database. 

mode | Database.model | Database.StorageEngineUsed
-----|----------------|---------------------------
Tabular 1200 and later| Returns the name of the model| StorageEngineUsed.TabularMetadata 
Tabular 1103, 1100, 1050 | Returns null | StorageEngineUsed.InMemory 
Multidimensional | Returns null | StorageEngineUsed.Traditional 

## Code example: List existing databases

The code below illustrates how to connect to the server and list databases hosted by server. 

```csharp
using System; using Microsoft.AnalysisServices; 
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
                // List common properties for the databases on the server. 
                // 
                foreach (Database db in server.Databases) 
                { 
                    Console.WriteLine("Properties for database {0}:", db.Name); 
                    Console.ForegroundColor = ConsoleColor.Yellow; 
                    Console.WriteLine("Database ID:\t\t\t{0}", db.ID); 
                    Console.WriteLine("Database compatibility level:\t{0}", db.CompatibilityLevel); 
                    Console.WriteLine("Database collation:\t\t{0}", db.Collation); 
                    Console.WriteLine("Database created timestamp:\t{0}", db.CreatedTimestamp); 
                    Console.WriteLine("Database language ID:\t\t{0}", db.Language); 
                    Console.WriteLine("Database model type:\t\t{0}", db.ModelType); 
                    Console.WriteLine("Database state:\t\t\t{0}", db.State); 
                    Console.ResetColor(); 
                    Console.WriteLine(); 
                } 
            } 
            Console.WriteLine("Press Enter to close this console window."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## Get an item from a database 

The following code snippet shows how to get a tabular or column from a database.

```csharp
var db = srv.Databases.GetByName("abc"); 

Column c1 = db.Model.Tables["foo"].Columns["bar"]; 
if (c1.ObjectType == ObjectType.Column) // always true 

MetadataObject obj; 

switch(obj.ObjectType) 
{ 
 case ObjectType.Table: 
  var t1 = (Table)obj; 
  break; 
} 
```
