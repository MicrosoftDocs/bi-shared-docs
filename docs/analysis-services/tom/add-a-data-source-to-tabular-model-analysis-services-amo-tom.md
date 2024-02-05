---
title: "Add a data source to tabular model (AMO-TOM) | Microsoft Docs"
description: Add a data source to a tabular model by adding an object of a class derived from DataSource to the DataSources collection of the Model object.
ms.date: 12/07/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: minewiskan

---
# Add a data source to tabular model (AMO-TOM)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

The **DataSource** class in the Microsoft.AnalysisServices.Tabular namespace is an abstraction of a tabular model's data source that specifies the type and location of imported data during a data refresh operation. 

You can add a data source to the tabular model by instantiating an object of a class derived from **DataSource**, and then add it to the **DataSources** collection of the Model object. To commit changes to the server, call either **Model.SaveChanges()** or **Database.Update(UpdateOptions.ExpandFull)**.

Tabular models support data import only from relational data sources, where the data provider exposes data in the form of tables and columns. As such, the tabular object model uses the ProviderDataSource class (derived from DataSource) to expose this capability.

## Code example: add a data source

This example demonstrate how to instantiate a **ProviderDataSource** and add it to a data model.

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
                    server.Databases.GetNewName("Database with a Data Source Definition"); 
 
                // 
                // Instantiate a new  
                // Microsoft.AnalysisServices.Tabular.Database object. 
                // 
                var dbWithDataSource = new Database() 
                { 
                    Name = newDatabaseName, 
                    ID = newDatabaseName, 
                    CompatibilityLevel = 1200, 
                    StorageEngineUsed = StorageEngineUsed.TabularMetadata, 
                }; 
 
                // 
                // Add a Microsoft.AnalysisServices.Tabular.Model object to the 
                // database, which acts as a root for all other Tabular metadata objects. 
                // 
                dbWithDataSource.Model = new Model() 
                { 
                    Name = "Tabular Data Model", 
                    Description = "A Tabular data model at the 1200 compatibility level." 
                }; 
 
                // 
                // Add a Microsoft.AnalysisServices.Tabular.ProviderDataSource object 
                // to the data Model object created in the previous step. The connection 
                // string of the data source object in this example  
                // points to an instance of the AdventureWorks2014 SQL Server database. 
                // 
                dbWithDataSource.Model.DataSources.Add(new ProviderDataSource() 
                { 
                    Name = "SQL Server Data Source Example", 
                    Description = "A data source definition that uses explicit Windows credentials for authentication against SQL Server.", 
                    ConnectionString = "Provider=SQLNCLI11;Data Source=localhost;Initial Catalog=AdventureWorks2014;Integrated Security=SSPI;Persist Security Info=false", 
                    ImpersonationMode = Microsoft.AnalysisServices.Tabular.ImpersonationMode.ImpersonateAccount, 
                    Account = @".\Administrator", 
                    Password = "P@ssw0rd", 
                }); 
 
                // 
                // Add the new database object to the server's  
                // Databases connection and submit the changes 
                // with full expansion to the server. 
                // 
                server.Databases.Add(dbWithDataSource); 
                dbWithDataSource.Update(UpdateOptions.ExpandFull); 
 
                Console.Write("Database "); 
                Console.ForegroundColor = ConsoleColor.Yellow; 
                Console.Write(dbWithDataSource.Name); 
                Console.ResetColor(); 
                Console.WriteLine(" created successfully."); 
                Console.WriteLine("The data model includes the following data source definitions:"); 
                Console.ForegroundColor = ConsoleColor.Yellow; 
                foreach (DataSource ds in dbWithDataSource.Model.DataSources) 
                { 
                    Console.WriteLine("\tData source name:\t\t{0}", ds.Name); 
                    Console.WriteLine("\tData source description:\t{0}", ds.Description); 
                } 
                Console.ResetColor(); 
                Console.WriteLine(); 
            } 
            Console.WriteLine("Press Enter to close this console window."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## Next step

Within a model, you'll need to set up data bindings that map source columns in the data source to destination columns in the model. You will also need to define the partitions, a minimum of one per table, that store the data. The following link shows you how: [Create tables, partitions, and columns](create-tables-partitions-and-columns-in-a-tabular-model.md)
