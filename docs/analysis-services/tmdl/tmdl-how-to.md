---
title: "Get started with Tabular Model Definition Language (TMDL) | Microsoft Docs"
description: Learn how to get started using the Tabular Model Definition Language (TMDL)
ms.date: 03/30/2023
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

Before completing this article, be sure to thoroughly understand TMDL concepts described in [Tabular Model Definition Language (TMDL) overview](tmdl-overview.md).

The easiest way to explore the Tabular Model Definition Language (TMDL) is to reference the preview Nuget package and use the API methods to serialize and deserialize to and from TMDL.

[Get the preview Nuget package](need url)

## Get a TMDL model representation

The following code example shows how to get a TMDL model representation of a dataset in a Power BI Premium workspace.

```tmdl
var workspaceXmla = " <Workspace XMLA address>";
var datasetName = "<dataset name>";
var outputPath = System.Environment.CurrentDirectory;

using (var server = new Server())
{
    server.Connect(workspaceXmla);

    var database = server.Databases.GetByName(datasetName);

    var destinationFolder = $"{outputPath}\\{database.Name}-tmdl";

    TmdlSerializer.SerializeModel(database.Model, older);

}

```

The output is a folder with a TMDL representation of the dataset.

:::image type="content" source="media/folder-tmdl-dataset.png" alt-text="Folder with a TMDL representation of a dataset":::

After serialization into a folder, you can use a text-editor to edit the TMDL files. For example, using VS Code we can add a new measure, **[Sales Amount (Computers)]**:

:::image type="content" source="media/sales-amount-computer-measure.png" alt-text="Sales amount computer measure in VS Code":::

## Deploy a TMDL model representation

The following code sample shows how to deploy a TMDL model representation of the dataset to a Power BI Premium workspace.

```tmdl
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