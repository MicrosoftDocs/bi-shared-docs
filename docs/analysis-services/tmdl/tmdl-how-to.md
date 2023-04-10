---
title: "Get started with Tabular Model Definition Language (TMDL) | Microsoft Docs"
description: Learn how to get started using the Tabular Model Definition Language (TMDL)
ms.date: 04/07/2023
ms.service: analysis-services
ms.custom: tmdl
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Get started with TMDL

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

> [!IMPORTANT]
> Tabular Model Definition Language (TMDL) is currently in preview. When in preview, functionality and documentation are likely to change.

Before getting started with this article, be sure to thoroughly understand concepts described in [Tabular Model Definition Language (TMDL) overview](tmdl-overview.md).

The easiest way to explore TMDL is to reference the **Preview Nuget package** and use the API methods to serialize and deserialize to and from TMDL.

[Get the **Preview Nuget packages**](../client-libraries.md#tmdl-preview)

## Get a TMDL model representation

The following code example shows how to get a TMDL model representation of a dataset in a Power BI Premium workspace:

```c#
var workspaceXmla = " <Workspace XMLA address>";
var datasetName = "<dataset name>";
var outputPath = System.Environment.CurrentDirectory;

using (var server = new Server())
{
    server.Connect(workspaceXmla);

    var database = server.Databases.GetByName(datasetName);

    var destinationFolder = $"{outputPath}\\{database.Name}-tmdl";

    TmdlSerializer.SerializeModel(database.Model, destinationFolder);

}

```

The output is a folder with a TMDL representation of the dataset, like this:

:::image type="content" source="media/folder-tmdl-dataset.png" alt-text="Folder with a TMDL representation of a dataset":::

After serialization into a folder, use a text-editor to edit the TMDL files. For example, by using VS Code we can add a new measure, **[Sales Amount (Computers)]**:

```tmdl
/// Sales data for year over year analysis
table Sales
    lineageTag: bb123cb2-11dc-4309-9793-d5e84bb2442c
    ordinal: 6

    partition 'Sales-3cf1ff71-eddc-4dfd-8fae-62e8f227e647' = M
        mode: Import
        attributes: ""
        expression:=
            let
                …
            in
                #"Filtered Rows1"

    measure 'Sales Amount' = SUMX('Sales', [Quantity] * [Net Price])
        formatString:= $ #,##0

    measure 'Sales Amount (Computers)' = CALCULATE([Sales Amount], 'Product'[Category] = "Computers")
        formatString:= $ #,##0

```

## Deploy a TMDL model representation

The following code example shows how to deploy a TMDL model representation of the dataset to a Power BI Premium workspace:

```c#
var xmlaServer = "<Workspace XMLA address>";

var tmdlFolderPath = $"{System.Environment.CurrentDirectory}\\Contoso-tmdl";

var model = TmdlSerializer.DeserializeModel(tmdlFolderPath);            

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

When executed, the new measure is deployed to the dataset.

:::image type="content" source="media/sales-amount-measure-in-dataset.png" alt-text="Sales Amount (Computers) measure in dataset ":::
