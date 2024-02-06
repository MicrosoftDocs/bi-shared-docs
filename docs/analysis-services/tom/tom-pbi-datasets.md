---
title: "Programming Power BI semantic models with the Tabular Object Model (TOM) | Microsoft Docs"
description: Overview of using the Tabular Object Model to create, view, and manage Power BI semantic models through the XMLA endpoint.
ms.date: 12/01/2021
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: tedpattison

---
# Programming Power BI semantic models with the Tabular Object Model (TOM)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

This article was originally created by the Power BI Customer Advisory Team (CAT) for [Power BI Dev Camp](https://www.powerbidevcamp.net/), a collection of sessions, articles, and videos about advanced programming for Power BI. 

Power BI Premium semantic models include the XMLA endpoint. The endpoint is significant to Power BI developers because it provides APIs to interact with the Analysis Services engine running in the Power BI Service and to directly program against Power BI models. A growing number of Power BI professionals have found that they can create, view and manage Power BI models by using pre-existing tools that use the XMLA protocol such as SQL Server Management Studio, Tabular Editor, and DAX Studio. As a .NET developer, you can now write C# code in a .NET application to create and modify models directly in the Power BI Service.

The Tabular Object Model (TOM) is a .NET library that provides an abstract layer on top of the XMLA endpoint. It allows developers to write code in terms of a intuitive programming model that includes classes like **Model**, **Table**, **Column**, and **Measure**. Behind the scenes, TOM translates the read and write operations in your code into HTTP requests executed against the XMLA endpoint.

:::image type="content" source="media/tom-pbi-datasets/endpoint-diagram.png" alt-text="Diagram of application to model through the XMLA endpoint." border="false":::

The focus of this article is getting started with TOM and demonstrating how to write the C# code required to create and modify models while they're running in the Power BI Service. However, TOM can also be used in scenarios that do not involve the XMLA endpoint, such as when programming against a local model running in Power BI Desktop. To learn more about using TOM with Power BI Desktop, see Power BI CAT member Phil Seamark's [blog series](https://dax.tips/2020/07/09/using-visual-studio-code-with-power-bi/), and be sure watch the [How to program datasets using the Tabular Object Model (TOM)](https://www.youtube.com/watch?v=Wt9jB2Had74) video from the Power BI Dev Camp.

TOM represents a new and powerful API for Power BI developers that is separate and distinct from the Power BI REST APIs. While there is some overlap between these two APIs, each of these APIs includes a significant amount of functionality not included in the other. Furthermore, there are scenarios that require a developer to use both APIs together to implement a full solution.

## Getting Started with the Tabular Object Model

The first thing you need to get before you can program with TOM is the URL for a workspace connection. The workspace connection URL references a specific workspace and is used to create a connection string that allows your code to connect to that Power BI workspace and the models running inside. Start by navigating to the **Settings** page of a Power BI workspace running in a dedicated capacity.

:::image type="content" source="media/tom-pbi-datasets/workspace-settings-nav.png" alt-text="Link to workspace Settings." border="false":::

> [!NOTE]
> XMLA endpoint is supported for models running in a dedicated capacity only. It's not available for models running in a shared capacity. If working with models in a Power BI Premium per User capacity, you can connect as a user but you cannot connect as a service principal.

Once you navigate to the **Premium** tab of the **Settings** pane, copy the Workspace Connection URL to the clipboard.

:::image type="content" source="media/tom-pbi-datasets/dataset-connection-string.png" alt-text="Workspace connection string in semantic model Settings." border="false":::

The next step is to create a new .NET application in which you write the C# code that programs using TOM. You can create a Web application or a Desktop application using .NET 5, .NET Core 3.1, or older versions on the .NET Framework. In this article we create a simple C# console application using the [.NET 5 SDK](https://dotnet.microsoft.com/download/dotnet/5.0).

### Create a new console application

Begin by using the [.NET CLI](/dotnet/core/tools/) to create a new console application.

```dotnetcli
dotnet new console --name`
```

#### Add the Tabular Object Model NuGet package

After creating the console application, add the **Microsoft.AnalysisServices.AdomdClient.NetCore.retail.amd64** NuGet package which contains the Tabular Object Model (TOM). You can install the package in a .NET 5 application by using the following .NET CLI:

```dotnetcli
dotnet add package Microsoft.AnalysisServices.NetCore.retail.amd64
```

#### Add the connection string

When your project has the NuGet package with the TOM library installed, you can then create the traditional **Hello World** application with TOM. The application connects to a Power BI workspace by using the Workspace Connection URL, and then enumerates through the models in the workspace and displays their names in the console window.

```dotnetcli
using System;
using Microsoft.AnalysisServices.Tabular;

class Program {
  static void Main() {

    // create the connect string
    string workspaceConnection = "powerbi://api.powerbi.com/v1.0/myorg/LearningTOM";
    string connectString = $"DataSource={workspaceConnection};";

    // connect to the Power BI workspace referenced in connect string
    Server server = new Server();
    server.Connect(connectString);

    // enumerate through models in workspace to display their names
    foreach (Database database in server.Databases) {
      Console.WriteLine(database.Name);
    }
  }
}
```

In this example, the connection string contains the Workspace Connection URL but no information about the user. If you run the console application with this code, the application will begin to run and then you'll be prompted with a browser-based window to log in. If you log in with a user account that has permissions to access the workspace referenced by the Workspace Connection URL, the TOM library is able to acquire an access token, connect to the Power BI Service, and enumerate through the models in the workspace.

To learn more about connecting through the XMLA endpoint, see [Sematic model connectivity with the XMLA endpoint - Connecting to a Premium workspace](/power-bi/admin/service-premium-connect-tools#connecting-to-a-premium-workspace).

#### Authenticating with user name and password

For development and testing scenarios where security is not as important, you can hard-code your user name and password, eliminating the need to log in interactively each time you run a program to test your code, as shown in the following code:

```dotnetcli
string workspaceConnection = "powerbi://api.powerbi.com/v1.0/myorg/YOUR_WORKSPACE";
string userId = "YOUR_USER_NAME";
string password = "YOUR_USER_PASSWORD";
string connectStringUser = $"DataSource={workspaceConnection};User ID={userId};Password={password};";
server.Connect(connectStringUser);
```

#### Authenticating with a service principal

It's also quite easy to authenticate as a service principal instead of as a user. If you've created a Microsoft Entra application with an Application ID and an application secret, you can authenticate your code to run as the service principal for the Microsoft Entra application by using the following code sample:

```dotnetcli
string workspaceConnection = "powerbi://api.powerbi.com/v1.0/myorg/YOUR_WORKSPACE";
string tenantId = "YOUR_TENANT_ID";
string appId = "YOUR_APP_ID";
string appSecret = "YOUR_APP_SECRET";
string connectStringApp = $"DataSource={workspaceConnection};User ID=app:{appId}@{tenantId};Password={appSecret};";
server.Connect(connectStringApp);
```

To program with TOM and access a model as a service principal, you must configure a tenant-level Power BI setting in the Power BI Admin portal. The steps for configuring Power BI to support connecting as a service principal is described in [Embed Power BI content with service principal and an application secret](/power-bi/developer/embedded/embed-service-principal).

<a name='authenticating-with-an-azure-ad-access-token'></a>

#### Authenticating with a Microsoft Entra access token

TOM also provides flexibility when establishing a connection using a valid Microsoft Entra access token. If you have the developer skills to implement an authentication flow with Microsoft Entra ID and acquire access tokens, you can format your TOM connection string without a user name, but include the access token as the password instead, as shown in the following code sample:

```dotnetcli
public static void ConnectToPowerBIAsUser() {
  string workspaceConnection = "powerbi://api.powerbi.com/v1.0/myorg/YOUR_WORKSPACE";
  string accessToken = TokenManager.GetAccessToken();  // you must implement GetAccessToken yourself
  string connectStringUser = $"DataSource={workspaceConnection};Password={accessToken};";
  server.Connect(connectStringUser);
}
```

If you're acquiring a user-based access token to connect to a Power BI workspace with TOM, be sure to request the following delegated permissions when acquiring access token to ensure you have all the authoring permissions you need:

```dotnetcli
public static readonly string[] XmlaScopes = new string[] {
    "https://analysis.windows.net/powerbi/api/Content.Create",
    "https://analysis.windows.net/powerbi/api/Dataset.ReadWrite.All",
    "https://analysis.windows.net/powerbi/api/Workspace.ReadWrite.All",
};
```

If you've been programming with the Power BI REST API, you might recognize familiar permissions such as **Content.Create**, **Dataset.ReadWrite.All** and **Workspace.ReadWrite.All**. An interesting observation is that TOM uses the same set of delegated permissions as the Power BI REST API defined within the scope of the Microsoft Entra resource ID of `https://analysis.windows.net/powerbi/api`.

The fact that both the XMLA endpoint and the Power BI REST API share the same set of delegated permissions has its benefits. Access tokens can be used interchangeably between TOM and the Power BI REST API. Once you have acquired an access token to call into TOM to create a new model, you can use the same access token to call the Power BI REST API to set the data source credentials, as described later in this article.

One thing that tends to confuse Power BI programmers is that service principals do not use delegated permissions. Instead, when programming with TOM you configure access for a service principal by adding it to the target workspace as a member in the role of Admin or Member.

## Understanding server, database, and model objects

The object model in TOM is based on a hierarchy with the top-level **Server** object which contains a collection of **Database** objects. When programing with TOM in Power BI, the **Server** object represents a Power BI workspace and the **Database** object represents a Power BI model.

:::image type="content" source="media/tom-pbi-datasets/object-model.png" alt-text="Tabular object model diagram with all objects" border="false":::

Each **Database** contains a **Model** object which provides read/write access to the data model. The **Model** contains collections for the elements of a data model including **DataSource**, **Table**, **Relationship**, **Perspective**, **Culture**, and **Role**.

As shown in the **Hello World** code, once you call **server.Connect**, you can easily discover what models exist inside a Power BI workspace by enumerating through the **Databases** collection of the **Server** object as shown in the following code:

```dotnetcli
foreach (Database database in server.Databases) {
    Console.WriteLine(database.Name);
}
```

You can also use the **GetByName** method exposed by the **Databases** collection object to access a model by name, like this:

```dotnetcli
Database database = server.Databases.GetByName("Wingtip Sales");
```

It's important to distinguish between a **Database**object and its inner **Model** property. You can use **Database** object properties to discover model attributes such as **Name**, **ID**, **CompatibilityMode**, and **CompatibilityLevel**. There's also an **EstimatedSize** property which makes it possible to discover how big a model has grown. Other properties include **LastUpdate**, **LastProcessed**, and **LastSchemaUpdate** which allow you to determine when the underlying model was last refreshed and when the model schema was lasted updated.

```dotnetcli
public static void GetDatabaseInfo(string DatabaseName) {
  Database database = server.Databases.GetByName(DatabaseName);
  Console.WriteLine("Name: " + database.Name);
  Console.WriteLine("ID: " + database.ID);
  Console.WriteLine("CompatibilityMode: " + database.CompatibilityMode);
  Console.WriteLine("CompatibilityLevel: " + database.CompatibilityLevel);
  Console.WriteLine("EstimatedSize: " + database.EstimatedSize);
  Console.WriteLine("LastUpdated: " + database.LastUpdate);
  Console.WriteLine("LastProcessed: " + database.LastProcessed);
  Console.WriteLine("LastSchemaUpdate: " + database.LastSchemaUpdate);
}
```

While the **Database** object has its own properties, it is the inner **Model** object of a **Database** object that provides you with the ability to read and write to a model's underlying data model. Here's a simple example of programming the database **Model** object to enumerate through its **Tables** collection and discover what tables are inside.

In the TOM object model, each **Table** object has collection objects for its partitions. columns, measures and hierarchies.

:::image type="content" source="media/tom-pbi-datasets/object-model-short.png" alt-text="Tabular object model diagram with Table, partition, column, measure, and hierarchy" border="false":::

Once you've retrieved the **Model** object for a **Database**, you can access a specific table by name in the model by using the **Find** method of the **Tables** collection. Here's an example retrieving a table named **Sales**, and discovering its members by enumerating through the **Columns** collection and **Measures** collection:

```dotnetcli
Model databaseModel = server.Databases.GetByName("Tom Demo").Model;

Table tableSales = databaseModel.Tables.Find("Sales");

foreach (Column column in tableSales.Columns) {
  Console.WriteLine("Coulumn: " + column.Name);
}

foreach (Measure measure in tableSales.Measures) {
  Console.WriteLine("Measure: " + measure.Name);
  Console.WriteLine(measure.Expression);
}
```

## Modifying models with TOM

In the sections above, you've seen how to access a **Database** object and its **Model** object to inspect the data model of a model running in the Power BI Service. Now it's time to program our first model update with TOM by adding a measure to a table.

The capacity you're using must be [enabled for XMLA read-write](/power-bi/admin/service-premium-connect-tools#enable-xmla-read-write). By default, the XMLA endpoint permissions setting is set to **Read**, so it must be explicitly set to **Read Write** by someone with **Capacity Admin** permissions. This setting can be viewed and updated in the **Capacity settings** page in the **Admin portal**.

:::image type="content" source="media/tom-pbi-datasets/xmla-read-write-setting.png" alt-text="XMLA Read Write setting in the Admin portal." border="false":::

When the XMLA endpoint has been configured for read-write, you can then add a new measure named **Sales Revenue** to the **Sales** table, as shown in the following code:

```dotnetcli
Model dataset = server.Databases.GetByName("Tom Demo Starter").Model;
Table tableSales = dataset.Tables.Find("Sales");
Measure salesRevenue = new Measure();
salesRevenue.Name = "Sales Revenue";
salesRevenue.Expression = "SUM(Sales[SalesAmount])";
salesRevenue.FormatString = "$#,##0.00";
tableSales.Measures.Add(salesRevenue);
dataset.SaveChanges();
```

Let's take a closer look at this code. First, you create a new **Measure** object using the C# **new** operator and provide values for the **Name**, **Expression**, and **FormatString**. You then add the new **Measure** object to the **Measures** collection of the target **Table** object by calling the **Add** method. Finally, call the **SaveChanges** method of the **Model** object to write your changes back to the model in the Power BI Service.

Keep in mind that updates to a model are batched in memory until you call **SaveChanges**. Imagine a scenario where you'd like to hide every column in a table. You can start by writing a **foreach** loop to enumerate through all the **Column** objects for a table and setting the **IsHidden** property for each **Column** object to true. After the **foreach** loop completes, you have several column updates that are batched in memory. But it's the final call to **SaveChanges** that push all the changes back to the Power BI Service in a batch, as shown below:

```dotnetcli
Model dataset = server.Databases.GetByName("Tom Demo").Model;
Table tableSales = dataset.Tables.Find("Sales");

foreach (Column column in tableSales.Columns) {
  column.IsHidden = true;
}

dataset.SaveChanges();
```

Let's say you want to update the **FormatString** property for an existing column. The **Columns** collection exposes a **Find** method to retrieve the target **Column** object. After that, it's just a matter of setting the **FormatString** property and calling **SaveChanges**, like this:

```dotnetcli
Model dataset = server.Databases.GetByName("Tom Demo").Model;
Table tableSales = dataset.Tables.Find("Products");
Column columnListPrice = tableSales.Columns.Find("List Price");
columnListPrice.FormatString = "$#,##0.00";
dataset.SaveChanges();
```

TOM's ability to dynamically discover what's inside a model provides opportunities to perform updates in a generic and sweeping fashion. Imagine a scenario in which you are managing a model which has lots of tables and tens or even hundreds of columns based on the **DateTime** datatype. You can update the **FormatString** property for each **DateTime** column in the entire model at the same by using the following:

```dotnetcli
Database database = server.Databases.GetByName("Tom Demo Starter");
Model datasetModel = database.Model;

foreach (Table table in datasetModel.Tables) {
  foreach (Column column in table.Columns) {
    if(column.DataType == DataType.DateTime) {
      column.FormatString = "yyyy-MM-dd";
    }
  }
}

datasetModel.SaveChanges();
```

## Refreshing models with TOM

Now let’s perform a typical model maintenance operation. As you  see in the following code, it's not very complicated to start a model refresh operation by using TOM:

```dotnetcli
public static void RefreshDatabaseModel(string Name) {
  Database database = server.Databases.GetByName(Name);
  database.Model.RequestRefresh(RefreshType.DataOnly);
  database.Model.SaveChanges();
}
```

Just like with manual and scheduled model refresh, refreshes through the XMLA endpoint are shown in **Refresh history**, but with the label, **Via XMLA Endpoint**.

:::image type="content" source="media/tom-pbi-datasets/refresh-history-via-xmla.png" alt-text="Refresh history dialog" border="false":::

> [!NOTE]
> While TOM provides the ability to start a refresh operation, it cannot set *data source credentials* for a Power BI model. In order to refresh models with TOM, you must first set the data source credentials in **Semantic model settings** or by using the Power BI REST APIs.

## Creating and cloning models

Imagine you have a requirement to create and clone Power BI models using code written in C#. Let’s begin by writing a reusable function named **CreateDatabase** that creates a new **Database** object, like this:

```csharp
public static Database CreateDatabase(string DatabaseName) {

  string newDatabaseName = server.Databases.GetNewName(DatabaseName);
  var database = new Database() {
    Name = newDatabaseName,
    ID = newDatabaseName,
    CompatibilityLevel = 1520,
    StorageEngineUsed = Microsoft.AnalysisServices.StorageEngineUsed.TabularMetadata,
    Model = new Model() {
      Name = DatabaseName + "-Model",
      Description = "A Demo Tabular data model with 1520 compatibility level."
    }
  };

  server.Databases.Add(database);
  database.Update(Microsoft.AnalysisServices.UpdateOptions.ExpandFull);
  return database;

}
```

In this example, we'll start by using the **GetNewName**method of the **Databases** collection object to ensure our new model name is unique within the target workspace. After that, the **Database** object and its **Model** object can be created by using the C# **new** operator as shown in the code below. At the end, this method adds the new **Database** object to the **Databases** collection and calls the **database.Update** method.

If your goal is to copy an existing model instead of creating a new one, you can use the following **CopyDatabase** method to clone a Power BI model by creating a new empty model and then calling **CopyTo** on the **Model** object for the source model to copy the entire data model into the newly created model.

```csharp
public static Database CopyDatabase(string sourceDatabaseName, string DatabaseName) {
  Database sourceDatabase = server.Databases.GetByName(sourceDatabaseName);
  string newDatabaseName = server.Databases.GetNewName(DatabaseName);
  Database targetDatabase = CreateDatabase(newDatabaseName);
  sourceDatabase.Model.CopyTo(targetDatabase.Model);
  targetDatabase.Model.SaveChanges();
  targetDatabase.Model.RequestRefresh(RefreshType.Full);
  targetDatabase.Model.SaveChanges();
  return targetDatabase;
}
```

## Creating a real-world model from scratch

OK, now imagine you've just created a new model from scratch and now you need to use TOM to compose a real-world data model by adding tables, columns, measures, hierarchies, and table relationships. Let's look at a code example that creates a new table that includes defined columns, adds a three-level dimensional hierarchy, and even supplies the M expression for the underlying table query:

```csharp
private static Table CreateProductsTable() {

  Table productsTable = new Table() {
    Name = "Products",
    Description = "Products table",
    Partitions = {
      new Partition() {
        Name = "All Products",
        Mode = ModeType.Import,
        Source = new MPartitionSource() {
          // M code for query maintained in separate source file
          Expression = Properties.Resources.ProductQuery_m
        }
      }
    },
    Columns = {
      new DataColumn() { Name = "ProductId", DataType = DataType.Int64, SourceColumn = "ProductId", IsHidden = true },
      new DataColumn() { Name = "Product", DataType = DataType.String, SourceColumn = "Product" },
      new DataColumn() { Name = "Description", DataType = DataType.String, SourceColumn = "Description" },
      new DataColumn() { Name = "Category", DataType = DataType.String, SourceColumn = "Category" },
      new DataColumn() { Name = "Subcategory", DataType = DataType.String, SourceColumn = "Subcategory" },
      new DataColumn() { Name = "Product Image", DataType = DataType.String, 
                        SourceColumn = "ProductImageUrl", DataCategory = "ImageUrl" }
     }
  };

  productsTable.Hierarchies.Add(
    new Hierarchy() {
      Name = "Product Category",
      Levels = {
        new Level() { Ordinal=0, Name="Category", Column=productsTable.Columns["Category"] },
        new Level() { Ordinal=1, Name="Subcategory", Column=productsTable.Columns["Subcategory"] },
        new Level() { Ordinal=2, Name="Product", Column=productsTable.Columns["Product"] }
      }
  });

  return productsTable;
}
```

Once you've created a set of helper methods to create the tables, you can then compose them together to create a data model, like this:

```csharp
Model model = database.Model;
Table tableCustomers = CreateCustomersTable();
Table tableProducts = CreateProductsTable();
Table tableSales = CreateSalesTable();
Table tableCalendar = CreateCalendarTable();
model.Tables.Add(tableCustomers);
model.Tables.Add(tableProducts);
model.Tables.Add(tableSales);
model.Tables.Add(tableCalendar);
```

TOM exposes a **Relationships** collection on the **Model** object which allows you to define the relationships between the tables in your model. Here's the code required to create a **SingleColumnRelationship** object which establishes a *one-to-many* relationship between the **Products** table and the **Sales** table:

```csharp
model.Relationships.Add(new SingleColumnRelationship {
  Name = "Products to Sales",
  ToColumn = tableProducts.Columns["ProductId"],
  ToCardinality = RelationshipEndCardinality.One,
  FromColumn = tableSales.Columns["ProductId"],
  FromCardinality = RelationshipEndCardinality.Many
});
```

After you're done adding the tables and table relationship, save your work with a call to **model.SaveChanges**:

```csharp
model.SaveChanges();
```

At this point, after calling **SaveChanges**, you should be able to see the new model created in the Power BI Service and begin using it to create new reports.

:::image type="content" source="media/tom-pbi-datasets/dataset-report.png" alt-text="Model report in the Power BI service." border="false":::

> [!IMPORTANT]
> Remember, you must specify data source credentials in Semantic model settings or through the Power BI REST API before you can refresh the model.

## Sample project

The sample project with the C# code you've seen in this article is available [here](https://github.com/PowerBiDevCamp/Tabular-Object-Model-Tutorial/blob/main/Demos/Learning-TOM/Learning-TOM/DatasetManager.cs). Now it's time for you to start programming with TOM and to find ways to leverage this powerful new API in the development of custom solutions for Power BI.

## See also

[Semantic model connectivity with the XMLA endpoint](/power-bi/admin/service-premium-connect-tools#connecting-to-a-premium-workspace)  
[Troubleshoot XMLA endpoint connectivity](/power-bi/admin/troubleshoot-xmla-endpoint)  
