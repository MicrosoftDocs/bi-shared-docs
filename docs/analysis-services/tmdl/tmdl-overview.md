---
title: "Tabular Model Definition Language (TMDL) | Microsoft Docs"
description: Learn about Tabular Model Definition Language (TMDL)
ms.date: 03/30/2023
ms.service: analysis-services
ms.custom: tmdl
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# Tabular Model Definition Language (TMDL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

> [!IMPORTANT]
> Tabular Model Definition Language (TMDL) is currently in preview. When in preview, functionality and documentation are likely to change.

Tabular Model Definition Language (TMDL) is an object model definition syntax for tabular data models at compatibility level 1200 or higher.

Key elements of TMDL include:

- Full compatibility with the entire [Tabular Object Model (TOM)](../tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo.md).
- Text-based and optimized for human interaction and readability. It uses the same grammar syntax as YAML. Each TMDL object is represented in text with minimal delimiters and uses indentation to demark its parent-child relationship.
- Better editing experience, especially on properties with embed expressions from different content-types, like DAX/M scripts.
- Better for collaboration because of its folder representation where each model object has an individual file representation, making it more source control friendly.

A particularly important aspect of TMDL is use of whitespace indentation to denote a TOM object structure. The following example shows how easy it is to represent a tabular model when using TMDL:

```tmdl
model Model
    compatibilityLevel: 1550
    culture: en-US
    ID: Sales

table Sales
partition 'Sales-Partition' = M
        mode: Import
        expression:= 
            let
                Source = Sql.Database(Server, Database)
                …
measure 'Sales Amount' = SUMX('Sales', 'Sales'[Quantity] * 'Sales'[Net Price])
        formatString:= $ #,##0
column Quantity
        dataType: Int64
        isHidden
        sourceColumn: Quantity
        summarizeBy: None
column 'Net Price'
        dataType: Int64
        isHidden
        sourceColumn: "Net Price"
        summarizeBy: None

table Product
partition 'Product-Partition' = M
        mode: Import
        expression:= 
            let
                Source = Sql.Database(Server, Database),
                …
column ProductKey
        dataType: Int64
        isKey
        sourceColumn: ProductKey
        summarizeBy: None

relationship 'cdb6e6a9-c9d1-42b9-b9e0-484a1bc7e123'
    fromColumn: Sales.ProductKey
    toColumn: Product.ProductKey

role Role_Store1
    modelPermission: Read

    tablePermission Store = [Store Code] IN {1,10,20,30}
        table: Store

expression Server = "localhost" meta [IsParameterQuery=true, Type="Text", IsParameterQueryRequired=true]

expression Database = "Contoso" meta [IsParameterQuery=true, Type="Text", IsParameterQueryRequired=true]

```

## TMDL API

Similar to TMSL, there's a class to handle TMDL Serialization. For TMDL, the class is  **TmdlSerializer**, under the Microsoft.AnalysisServices.Tabular namespace.

The TmdlSerializer class exposes two public methods:

`public static Model DeserializeModel(string path)`

- Receives a full path to a TMDL folder.
- Returns the TOM model object representation of the TMDL folder.

`public static void SerializeModel(Model model, string path)`

- Receives a TOM model object and the TMDL output path.
- Serializes the TOM model into a TMDL folder representation.

#### Handling errors in the TMDL API

When an error is detected in TMDL serialization methods, besides throwing a few common .NET exceptions like `ArgumentException` and `InvalidOperationException`, TMDL can also return TMDL-specific exceptions.

TmdlFormatException is returned during TMDL folder deserialization. In addition to exception details, the following is included:

- Path
        - Path to the TMDL file with errors
- LineNumber
        - Line number with errors
- LineText
        - Line text with errors

Code example handling `TmdlFormatException`.

```csharp
try
        {
            var tmdlPath = "<TMDL Folder Path>";

            var model = TmdlSerializer.DeserializeModel(tmdlPath);
        }
        catch (TmdlFormatException ex)
        {
            var errorMsg = ex.Message;
            var path = ex.Path;
            var line = ex.LineNumber;
            var lineText = ex.LineText;

            Console.WriteLine($"Error on Deserializing TMDL '{errorMsg}', path: '{path}'  line: '{line}', line text: '{lineText}'");
            throw;
        }    

```

## TMDL folder structure

Unlike TMSL, TMDL implements a folder structure. The default folder structure has only one level of *sub-folders*, all with inner .tmd files:

- cultures
- perspectives
- roles
- tables

And *root files* for:

- dataSources
- model
- relationships

Here's an example of a TMDL folder.

:::image type="content" source="media/folder-tmdl-dataset.png" alt-text="Folder with a TMDL representation of a dataset":::

Definitions include:

- One file for model definition
- One file for all relationships in the model 
- One file for each culture linguistic schema 
- One file for each translation (in CSV format) along side culture linguistic schema
- One file for each perspective
- One file for each role
- One file for each table
- All inner metadata properties of tables (Column, Hierarchies, Partitions,…)  metadata lives in the parent table TMD file

## TMDL language

### Object declaration

Except for Server and Database objects, TMDL exposes the entire TOM *Model* object tree in the [Microsoft.AnalysisServices.Tabular namespace](/dotnet/api/microsoft.analysisservices?view=analysisservices-dotnet&preserve-view=true). For example, in the following image you see the Table object type in TMDL shows all of the properties, collections, and child-objects from the [Table Class](/dotnet/api/microsoft.analysisservices.tabular.table?view=analysisservices-dotnet&preserve-view=true).

:::image type="content" source="media/object-classes-diagram.png" alt-text="Object classes diagram":::

A TMDL object is declared by specifying the TOM object type followed by its name. In the following code example, you see each object type: model, table, partition, measure, column, and another column are followed by an object name. While database isn't a valid TMDL object, compatibilityLevel, culture, and ID properties from the database object are exposed in the TMDL model object.

```tmdl
model Model
    compatibilityLevel: 1550
    culture: en-US
    ID: Sales

table Sales

partition 'Sales-Partition' = M
        expression:= 
            let
              Source = Sql.Database(Server, Database)
             …
            in
                #"Removed Columns"
    
    measure Sales= SUM(…)
        formatString:= $ #,##0

    column Customer_Key
        datatype: Int64
        sourceColumn: "CustomerKey"
    column 'Order Date'
        dataType: DateTime
        sourceColumn: "OrderDate"

```

### Partial  declaration

TMDL doesn't force object declaration in the same document. It is, however, similar to [C# partial classes](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods) where it's possible split the object definition between multiple files. For example, it's possible to declare a table definition in a [table].tmd file and then have all the measures from all tables defined in a single [measures].tmd file, like shown here:

```tmdl
table Table1

measure Measure1 = SUM(…)
        formatString:= $ #,##0

table Table2

measure Measure1 = SUM(…)
        formatString:= $ #,##0

```

To avoid a parsing error, the same property can't be declared twice. For example, declaring  two measures with same name for the same table in two different TMDL documents results in an error.

### Object reference

Within a TMDL document, there are situations where you need to reference an object from another object, like in partitions. An object reference should be by name. If the name includes a non-alphanumeric or an underscore character, it should be enclosed in quotes. For example:

- Partition_sales_2023
- 'partition sales – 2023'
- 'partition "sales – 2023"' (In TOM, this reference would be "partition 'sales – 2023'")

If needed to reference a fully qualified name, TMDL uses dot notation to reference an object from another object, as shown in the following example:

```tmdl
perspective Perspective1

    perspectiveTable Table1
        table: Table1

        perspectiveColumn Col1
            column: 'Table1'.Col1
        
        perspectiveColumn 'Col 2'
            column: 'Table1'.'Col 2'
```

### Descriptions

TMDL syntax supports descriptions. For model documentation purposes, it's considered a best practice to provide descriptions for each TOM object. TMDL treats descriptions as a special property with explicit syntax support. Following the examples from many other languages, descriptions are provided on top of each object declaration using triple-slash  (**///**) syntax.

No whitespace is allowed between the description block end and the object type token.

Descriptions can be split across multiple lines. The TMDL serializer breaks object descriptions into multiple lines in-order to keep emitted document lines within a certain maximum length. The default is 80 characters.

```tmdl
/// Table Description
table Table1
    prop1: value
        
    /// This is the Measure Description
    /// One more line
    measure Measure1 = SUM(...)
        formatString:= #,##0

```

### Default properties

In addition to special treatment of name and description, some object types have a default property that most of the time are treated like expressions during TMDL parsing. The default property is object type specific and where applicable the property value is provided following the equals (**=**) delimiter, after the section declaration.

Two possible syntaxes are supported:

- The value is specified on the same line as the section header.
- The value is specified  as a multi-line block following the section header. Outer left indentation of the expression isn't considered.

In the following example, Measure1 is single line and Measure2 is a multi-line block:

```tmdl
table Table1
    
    partition 'partition 1' = M
        expression:= ```
            let
            ...
            in
                #finalStep
            ```
        mode: Import
    
    measure Measure1 = SUM(...)
        formatString:= #,##0
        boolProp

    measure 'Measure 2' = ```
        SUMX ( 
            ...
        )
        ```
        formatString:= $ #,##0

```

#### Default properties by object type

Default property and expression language by object type include the following:

|Object type    |Default property  |Expression language  |
|---------|---------|---------|
|Measure     |  Expression       |    DAX     |
|CalculatedColumn    |  Expression       |    DAX     |
|CalculationItem    |  Expression       |   DAX      |
|FormatStringDefinition     |  Expression      |   DAX      |
|DetailRowsDefinition     |  Expression       |   DAX      |
|CalculationExpression     |   Expression      |   DAX      |
|DataCoverageDefinition     |  Expression       |   DAX      |
|TablePermission    |  FilterExpression       |    DAX     |
|ColumnPermission    |   MetadataPermission      |    [MetadataPermission Enum](/dotnet/api/microsoft.analysisservices.tabular.metadatapermission?view=analysisservices-dotnet&preserve-view=true)     |
|NamedExpression     |   Expression      |    M     |
|JsonExtendedProperty     |   Value      |    Json     |
|Annotation     |    Key & Value     |   Text      |
|StringExtendedProperty     |   Value      |    Text     |
|DataSource    |    Type     |    [DataSourceType Enum](/dotnet/api/microsoft.analysisservices.tabular.datasourcetype?view=analysisservices-dotnet&preserve-view=true)     |
|Partition     |    SourceType     |    [PartitionSourceType Enum](/dotnet/api/microsoft.analysisservices.tabular.partitionsourcetype?view=analysisservices-dotnet&preserve-view=true)     |
|ChangedProperty     |   Property      |    [Property Text](/dotnet/api/microsoft.analysisservices.tabular.changedproperty.property?view=analysisservices-dotnet&preserve-view=true#microsoft-analysisservices-tabular-changedproperty-property)     |

### Expressions

Despite being a string scalar in TOM, in TMDL, certain object properties get a special parsing. The entire text is read verbatim because it can include special characters like quotes or square brackets in M or DAX expressions.

An expression value in TMDL is provided following a colon and equals delimiter (**:=**) enclosed with the three backticks (**```**), like in the following example:

```tmdl
table Table1
    prop1: value
    bool1
    struct:
            prop1: value
            prop2: value
    
    partition 'partition 1' = M
        expression:= ```
            let
            ...
            in
                #finalStep
            ```
        mode: Import
    
    measure Measure1 = SUM(...)
        formatString:= #,##0
        boolProp

    measure 'Measure 2' = ```
        SUMX ( 
            ...
        )
    ```
        formatString:= $ #,##0
```

The following special rules apply to expressions:

- All outer indentation whitespace are stripped beyond the indented level of the parent object. Relative indentation within the expression is retained. The end delimiter (**```**) determines the expression left boundary (see 'Measure 2' in the previous example).
- New lines and indentation are preserved, making it easy to copy and paste DAX and M expressions into TMDL.

The following properties are treated as expressions and should be delimited with a colon and equals sign  (**:=**):

|Object Type |Property  |Expression language  |
|---------|---------|---------|
|CalculatedPartitionSource    |    Expression     |   DAX      |
|MPartitionSource     |    Expression     |    M     |
|QueryPartitionSource     |    Query     |    NativeQuery    |
|LinguisticMetadata     |    Content     |    XML or Json     |
|Measure     |    FormatString     |    [VBA style custom format string](/power-bi/create-reports/desktop-custom-format-strings#supported-custom-format-syntax)     |
|Column     |   FormatString      |    [VBA style custom format string](/power-bi/create-reports/desktop-custom-format-strings#supported-custom-format-syntax)      |
|BasicRefreshPolicy     |    SourceExpression     |     M    |
|BasicRefreshPolicy     |     PollingExpression    |    M     |
|KPI     |    StatusExpression     |     DAX    |
|KPI     |   TargetExpression     |     DAX    |
|KPI     |   TargetExpression     |     DAX    |

### Multi-line / Block

TMDL supports multi-line blocks of embedded expressions as property values. Blocks are delimited by using three backtick (**```**) notation. The delimiter should be applied immediately following the colon and equal sign (**:=**) and after the line following the expression, like in the following example:

```tmdl
table Table1
    prop1: value
    bool1
    struct:
            prop1: value
            prop2: value

    partition 'partition 1' = M
        expression:= ```
            let
            ...
            in
                #finalStep
            ```
        mode: Import
```

Everything between three backticks (**```**) is considered part of the multi-block expression and TMDL indentation rules aren't applied. The end delimiter determines the indentation within the expression.

### Child objects

The TOM object tree contains child objects in many places and at different levels. For example:

- A model object contains table, role, and expression objects.
- A table object contains column, measure, and hierarchy objects.

TMDL doesn't declare child collections explicitly. Instead, all applicable child elements within the scope of their respective parent implicitly make up the elements of the corresponding collection. For example, all column elements within the scope of a particular table become elements of the columns collection of that table in TOM, like shown here:  

```tmdl
table Sales

    measure 'Sales Amount' = SUMX('Sales', [Quantity] * [Net Price])

    measure 'Total Quantity' = SUM('Sales'[Quantity])

    measure 'Sales Amount YTD' = TOTALYTD([Sales Amount], 'Calendar'[Date])

    measure 'Sales Amount (ly)' = CALCULATE([Sales Amount], SAMEPERIODLASTYEAR('Calendar'[Date]))

```

Child objects don't have to be contiguous. You can declare columns and measures in any order.

## Considerations and limitations

- line item.
- line item.
- line item.

## What's next?

Now that you have an understanding of TMDL, be sure to see [Get started with TMDL](tmdl-how-to.md) to learn how to get and deploy a TMDL model representation of a Power BI dataset.
