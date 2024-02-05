---
title: "Get started with Tabular Model Definition Language (TMDL) | Microsoft Docs"
description: Learn how to get started using the Tabular Model Definition Language (TMDL)
ms.date: 12/20/2023
ms.service: analysis-services
ms.custom: tmdl
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Get started with TMDL

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

> [!IMPORTANT]
> Tabular Model Definition Language (TMDL) is currently in preview. When in preview, functionality and documentation are likely to change.

Before getting started with this article, be sure to thoroughly understand concepts described in [Tabular Model Definition Language (TMDL) overview](tmdl-overview.md).

The easiest way to explore TMDL is to reference the  Analysis Services Management Objects (AMO) **Nuget package** and use the TMDL API methods to serialize and deserialize to and from TMDL.

[Get the **Nuget packages**](../client-libraries.md#nuget-packages)

## Get a TMDL model representation

The following code example shows how to get a TMDL model representation of a semantic model in a Power BI Premium workspace:

```c#
var workspaceXmla = " <Workspace XMLA address>";
var datasetName = "<dataset name>";
var outputPath = System.Environment.CurrentDirectory;

using (var server = new Server())
{
    server.Connect(workspaceXmla);

    var database = server.Databases.GetByName(datasetName);

    var destinationFolder = $"{outputPath}\\{database.Name}-tmdl";

    TmdlSerializer.SerializeDatabaseToFolder(database.Model, destinationFolder);

}

```

The output is a folder with a TMDL representation of the model, like this:

:::image type="content" source="media/folder-tmdl-dataset.png" alt-text="Folder with a TMDL representation of a model":::

After serialization into a folder, use a text-editor to edit the TMDL files. For example, by using Visual Studio Code we can add a new measure, **[Sales Amount (Computers)]**:

```tmdl
/// Sales data for year over year analysis
table Sales        

    partition 'Sales-Part1' = m
        mode: Import        
        source =
            let
                …
            in
                #"Filtered Rows1"

    measure 'Sales Amount' = SUMX('Sales', [Quantity] * [Net Price])
        formatString: $ #,##0

    measure 'Sales Amount (Computers)' = CALCULATE([Sales Amount], 'Product'[Category] = "Computers")
        formatString: $ #,##0

```

For a better experience you can install [Visual Studio Code TMDL language extension](https://marketplace.visualstudio.com/items?itemName=analysis-services.TMDL).

## Deploy a TMDL model representation

The following code example shows how to deploy a TMDL model representation of the model to a Power BI Premium workspace:

```c#
var xmlaServer = "<Workspace XMLA address>";

var tmdlFolderPath = $"{System.Environment.CurrentDirectory}\\Contoso-tmdl";

var model = TmdlSerializer.DeserializeDatabaseFromFolder(tmdlFolderPath);            

using (var server = new Server())
{
    server.Connect(xmlaServer);

    using (var remoteDatabase = server.Databases[model.Database.ID])
    {
        model.CopyTo(remoteDatabase.Model);

        remoteDatabase.Model.SaveChanges();
    }               
}

```

When executed, the new measure is deployed to the model.

:::image type="content" source="media/sales-amount-measure-in-dataset.png" alt-text="Sales Amount (Computers) measure in dataset ":::

## Handling TMDL serialization errors

When an error is detected in TMDL serialization methods, besides throwing a few common .NET exceptions like `ArgumentException` and `InvalidOperationException`, TMDL-specific exceptions are also returned.

- `TmdlFormatException` is thrown if the TMDL text is not a valid syntax. For example, invalid keyword or indentation.

- `TmdlSerializationException` is thrown if the TMDL text is valid, but violates the TOM metadata logic. For example, type of value does not match the expected type.

In addition to exception details, the following is included:

- `document path`: Path to the TMDL file with errors.
- `line number`: line number with errors.
- `line text`: line text with errors.

Code example handling `TmdlFormatException`:

```csharp
try
{
    var tmdlPath = "<TMDL Folder Path>";

    var model = TmdlSerializer.DeserializeDatabaseFromFolder(tmdlPath);
}
catch (TmdlFormatException ex)
{
    Console.WriteLine($"Error on Deserializing TMDL '{ex.Message}', document path: '{ex.Document}'  line number: '{ex.Line}', line text: '{ex.LineText}'");

    throw;
}    

```

## Object text serialization

The following code example shows how to serialize a column into TMDL:

```csharp

var output = TmdlSerializer.SerializeObject(model.Tables["Product"].Columns["ProductKey"], qualifyObject: true);

Console.WriteLine(output);

```

Output:

```tmdl
ref table Product

 column ProductKey
  dataType: int64
  isKey
  formatString: 0
  isAvailableInMdx: false
  lineageTag: 4184d53e-cd2d-4cbe-b8cb-04c72a750bc4
  summarizeBy: none
  sourceColumn: ProductKey

  annotation SummarizationSetBy = Automatic
```

## Stream serialization

The following code example shows how to serialize a semantic model to a single text variable:

```csharp
var output = new StringBuilder();

foreach (MetadataDocument document in model.ToTmdl())
{
    using (TextWriter writer = new StringWriter(output))
    {
        document.WriteTo(writer);
    }
}

Console.WriteLine(output.ToString());

```

The following code example shows how to deserialize from TMDL, excluding the roles:

```csharp
var context = MetadataSerializationContext.Create(MetadataSerializationStyle.Tmdl);

var files = Directory.GetFiles("[TMDL Directory Path]", "*.tmdl", SearchOption.AllDirectories);

foreach (var file in files)
{
    if (file.Contains("/roles/"))
        continue;

    using (TextReader reader = File.OpenText(file))
    {                    
        context.ReadFromDocument(file, reader);
    }
}

var model = context.ToModel();

```
