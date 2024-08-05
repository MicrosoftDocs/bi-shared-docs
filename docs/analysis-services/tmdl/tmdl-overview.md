---
title: "Tabular Model Definition Language (TMDL) | Microsoft Docs"
description: Learn about Tabular Model Definition Language (TMDL)
ms.date: 12/27/2023
ms.service: analysis-services
ms.custom: tmdl
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# Tabular Model Definition Language (TMDL)

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

Tabular Model Definition Language (TMDL) is an object model definition syntax for tabular data models at compatibility level 1200 or higher.

Key elements of TMDL include:

- Full compatibility with the entire [Tabular Object Model (TOM)](../tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo.md). Every TMDL object exposes the same properties as TOM.
- Text-based and optimized for human interaction and readability. TMDL uses a grammar syntax similar to YAML. Each TMDL object is represented in text with minimal delimiters and uses indentation to demark parent-child relationships.
- Better editing experience, especially on properties with embed expressions from different content-types, like Data Analysis Expression (DAX) and M.
- Better for collaboration because of its folder representation where each model object has an individual file representation, making it more source control friendly.

An important aspect of TMDL is use of whitespace indentation to denote a TOM object structure. The following example shows how easy it is to represent a tabular model when using TMDL:

```tmdl
database Sales
	compatibilityLevel: 1567

model Model    
    culture: en-US    

table Sales
    
    partition 'Sales-Partition' = m
        mode: import
        source = 
            let
                Source = Sql.Database(Server, Database)
                …
    
    measure 'Sales Amount' = SUMX('Sales', 'Sales'[Quantity] * 'Sales'[Net Price])
        formatString: $ #,##0
   
    column 'Product Key'
        dataType: int64
        isHidden
        sourceColumn: ProductKey
        summarizeBy: None
 
    column Quantity
        dataType: int64
        isHidden
        sourceColumn: Quantity
        summarizeBy: None

    column 'Net Price'
        dataType: int64
        isHidden
        sourceColumn: "Net Price"
        summarizeBy: none

table Product
    
    partition 'Product-Partition' = m
        mode: import
        source = 
            let
                Source = Sql.Database(Server, Database),
                …

    column 'Product Key'
        dataType: int64
        isKey
        sourceColumn: ProductKey
        summarizeBy: none

relationship cdb6e6a9-c9d1-42b9-b9e0-484a1bc7e123
    fromColumn: Sales.'Product Key'
    toColumn: Product.'Product Key'

role Role_Store1
    modelPermission: read

    tablePermission Store = 'Store'[Store Code] IN {1,10,20,30}

expression Server = "localhost" meta [IsParameterQuery=true, Type="Text", IsParameterQueryRequired=true]

expression Database = "Contoso" meta [IsParameterQuery=true, Type="Text", IsParameterQueryRequired=true]

```

## TMDL folder structure

Unlike TMSL, TMDL uses a folder structure. The default folder structure has only one level of *sub-folders*, all with .tmdl files inside:

- cultures
- perspectives
- roles
- tables

And *root files* for:

- database
- model
- relationships
- expressions
- datasources

Here's an example of a TMDL folder:

:::image type="content" source="media/folder-tmdl-dataset.png" alt-text="Folder with a TMDL representation of a model":::

Definitions include:

- One file for database definition.
- One file for model definition.
- One file for *all* datasources in the model.
- One file for *all* expressions in the model.
- One file for *all* relationships in the model.
- One file for *each* culture linguistic schema.
- One file for *each* perspective.
- One file for *each* role.
- One file for *each* table.
- All inner metadata properties of tables (Column, Hierarchies, Partitions,…) metadata lives in the parent table TMDL file.


## TMDL API

Similar to [Tabular Model Scripting Language (TMSL)](../tmsl/tabular-model-scripting-language-tmsl-reference.md), there's a class to handle TMDL Serialization. For TMDL, the class is  [**TmdlSerializer**](/dotnet/api/microsoft.analysisservices.tmdlserializer), under the [**Microsoft.AnalysisServices.Tabular**](/dotnet/api/microsoft.analysisservices.tabular) namespace.

The TmdlSerializer class exposes methods to serialize and deserialize TMDL documents:

### Folder Serialization

`public static void SerializeDatabaseToFolder (Database database, string path)`

- Receives a TOM database object and the TMDL output path.
- Serializes the TOM database into a TMDL folder representation.

Learn more [about how to serialize to a folder](tmdl-how-to.md?#get-a-tmdl-model-representation).

`public static Database DeserializeDatabaseFromFolder (string path)`

- Receives a full path to a TMDL folder.
- Returns the TOM database object representation of the TMDL folder.

Learn more [about how to deserialize from folders](tmdl-how-to.md?#deploy-a-tmdl-model-representation).

### String Serialization

`public static string SerializeObject (MetadataObject object, bool qualifyObject = true)`

- Receives a TOM object and returns its TMDL text representation.

Learn more [about how serialize an object to a string](tmdl-how-to.md?#object-text-serialization).

### Stream Serialization

You can serialize/deserialize TMDL to/from streams, allowing you to convert a TOM object into byte streams for storage, transmission, and interoperability across platforms. The Stream API also allows you to control which TMDL documents are loaded and which TMDL documents are outputted.

TMDL Stream serialization is handled by the [**MetadataSerializationContext**](/dotnet/api/microsoft.analysisservices.tabular.serialization.metadataserializationcontext) class.

Learn more [about how to serialize to/from TMDL using streams](tmdl-how-to.md?#stream-serialization).

## TMDL language

### Object declaration

Except for Server object, TMDL exposes the entire TOM *Database* object tree in the [Microsoft.AnalysisServices.Tabular namespace](/dotnet/api/microsoft.analysisservices).

A TMDL object is declared by specifying the TOM object type followed by its name. In the following code example, each object type: `model`, `table`, `column` is followed by an object name.

```tmdl
model Model    
    culture: en-US    

table Sales
    
    measure Sales = SUM(…)
        formatString: $ #,##0

    column 'Customer Key'
        datatype: int64
        sourceColumn: CustomerKey

```

Objects like `partition` or `measure` have [default properties](#default-properties) that can be assigned after the equals (**=**) delimiter in the same line of the object declaration or in the following line for a multi-line [expression](#expressions):

```tmdl
table Sales

    partition Sales-Part1 = m
        mode: import
        ...        
    
    measure Sales = SUM(…)
        formatString: $ #,##0

    measure 'Sales (ly)' = 
            var ly = ...
            return ly
        formatString: $ #,##0
```

The TMDL object name must be enclosed in single quotes (**'**) if it includes any of the following characters:

- Dot (**.**)
- Equals (**=**)
- Colon (**:**)
- Single Quote (**'**)
- Whitespace ( )

If an object name contains single quotes (**'**), use two single quotes to escape it.

### Object Properties

Object properties are specified after the object declaration or object default property multi-line expression. Object property values are specified following the colon (**:**) delimiter. For example:

```tmdl
table Sales
    lineageTag: e9374b9a-faee-4f9e-b2e7-d9aafb9d6a91    

    column Quantity
        dataType: int64
        isHidden
        isAvailableInMdx: false
        sourceColumn: Quantity

    measure 'Sales Amount' = 
            var result = SUMX(...)
            return result
  formatString: $ #,##0
  displayFolder: " My ""Amazing"" Measures"

```

The following rules apply to property values:

- Value must be in the same line following the colon and cannot have multiple lines.

- Text property values

  - Leading and trailing Double-quotes are optional and automatically stripped during serialization.
  - Must be enclosed in double quotes (**"**) if the text contains trailing or leading whitespace.
  - When enclosed in double quotes, if the value contains double quotes, use two double quotes to escape them (see `displayFolder` property in the code example above).

- **Boolean properties** can be set by using standard key/value pair syntax, like with the `'isAvailableInMdx'` property in the previous example. They can also be set by using a shortcut syntax where only the property name is declared and `true` is implied. See, for example, the 'isHidden' property in the previous example.

#### Named object references

Some object properties hold references to other model objects, for example:

- Column reference in hierarchy levels.
- sortByColumn reference in each table column.
- Table/column/measure reference in perspectives.

In TMDL, references are made using the object name and follow the same escaping and single-quote (**'**) enclosing requirements of object declaration. In the following code example, you see object properties that hold a reference to another object: `column.sortByColumn`, `level.column`, `perspectiveMeasure.measure` and `perspectiveTable.table`.

```tmdl

table Product

    column Category
        sortByColumn: 'Category Order'    

 hierarchy 'Product Hierarchy'

  level Category   
   column: Category  
 

perspective Product

 perspectiveTable Product

        perspectiveMeasure '# Products'

```

If needed to reference a fully qualified name, TMDL uses *dot* notation to reference an object, for example: `'Table 1'.'Column 1'`

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

```

Child objects don't have to be contiguous. For example, you can declare columns and measures in any order and intermingled.

### Default properties

Some object types have a default property that most of the time are treated like [expressions](#expressions). The default property is object type specific. Where applicable, the property value or expression is specified following the equals (**=**) delimiter - after the section declaration.

Supported syntax:

- The value is specified on the same line as the section header.
- The value is specified as a multi-line expression following the section header.

In the following code example, measure `Sales Amount` and partition `Sales-Partition1` are single line and measure `Quantity` is multi-line:

```tmdl
table Sales

    measure 'Sales Amount' = SUM(...)
        formatString: $ #,##0

    measure Quantity = 
            var result = SUMX (...)
            return result
        formatString: #,##0

    partition Sales-Partition1 = m
  mode: import
  source =
   let
       ...
   in
       finalStep

```

### Expressions

There are object properties that, while being a text property in TOM, get special parsing in TMDL. The entire text is read verbatim because it can include special characters like quotes or square brackets in M or DAX expressions. Expressions could be multi-line or single-line. If multi-line, they must be located in the line immediately following the property or object declaration.

An expression value in TMDL is specified following a equals (**=**) delimiter, like in the following example:

```tmdl
table Table1

    partition 'partition 1' = m
        mode: import
        source =
            let
            ...
            in
                finalStep
    
    measure Measure1 = SUM(...)

    measure Measure2 =
            var result = SUMX ( 
                ...
            )
            return result
        formatString: $ #,##0

```

The following special rules apply to expressions:

- Multi-line expressions must be indented one level deeper to the parent object properties and the entire expression must be within that indentation level.
- All outer indentation whitespaces are stripped beyond the indented level of the parent object.
- Vertical whitespaces (blank lines without whitespaces) are allowed and are considered part of the expression.
- Trailing blank lines and whitespaces are removed.
- To enforce a different indentation or to preserve trailing blank lines or whitespaces, use the three backticks (**```**) enclosing.
- By default, TMDL serializer will enclose with backticks if the expression value contains anything that could cause a modification on roundtrip (for example, trailing whitespaces, blank lines with whitespaces).

Expressions enclosed with three backticks (**```**) are read verbatim including indentation, blank lines and whitespaces. The delimiter should be applied immediately following the equal sign (**=**) and the line following the expression and cannot have anything after it, like in the following example:

```tmdl
table Table1

    partition partition1 = m
        mode: import
        source = ```
            let
            ...
            in
                finalStep

            ```

    measure Measure1 = ```
                var myVar = Today()
                …
                return result
            ```

```

Using the three backticks (**```**) delimiter is optional and only required in unique situations. For most situations, using correct indentation and object declaration ensures correct parsing of whatever expression you add to the property.

When the expression is enclosed within backticks, the following rules apply:

- Everything between three backticks (**```**) is considered part of the multi-block expression and TMDL indentation rules aren't applied. The end delimiter determines the indentation within the expression.
- Relative indentation within the expression is retained. The end delimiter (**```**) determines the expression left boundary (see 'Measure1' in the previous example).

The following properties are treated as expressions:

|Object Type |Property  |Expression language  |
|---------|---------|---------|
|Measure     |   Expression     |     DAX    |
|MPartitionSource     |    Expression     |    M     |
|CalculatedPartitionSource    |    Expression     |   DAX      |
|QueryPartitionSource     |    Query     |    NativeQuery    |
|CalculationItem     |   Expression     |     DAX    |
|BasicRefreshPolicy     |    SourceExpression, PollingExpression     |     M    |
|KPI     |    StatusExpression, TargetExpression, TrendExpression     |     DAX    |
|LinguisticMetadata     |    Content     |    XML or Json     |
|JsonExtendedProperty     |    Value     |    Json     |
|FormatStringDefintion     |    Expression     |    DAX     |
|DataCoverageDefinition     |    Expression     |    DAX     |
|CalculationGroupExpression     |    Expression     |    DAX     |
|NamedExpression     |    Expression     |    DAX     |
|DetailRowsDefinition     |    Expression     |    DAX     |
|TablePermission     |    FilterExpression     |    DAX     |
|CalculatedColumn     |    Expression     |    DAX     |

#### Default properties by object type

The following table shows default property and expression language by object type:

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
|ColumnPermission    |   MetadataPermission      |    [MetadataPermission Enum](/dotnet/api/microsoft.analysisservices.tabular.metadatapermission)     |
|NamedExpression     |   Expression      |    M     |
|MPartitionSource     |   Expression      |    M     |
|CalculatedPartitionSource     |   Expression      |    DAX     |
|JsonExtendedProperty     |   Value      |    Json     |
|Annotation     |    Value     |   Text      |
|StringExtendedProperty     |   Value      |    Text     |
|DataSource    |    Type     |    [DataSourceType Enum](/dotnet/api/microsoft.analysisservices.tabular.datasourcetype)     |
|Partition     |    SourceType     |    [PartitionSourceType Enum](/dotnet/api/microsoft.analysisservices.tabular.partitionsourcetype)     |
|ChangedProperty     |   Property      |    [Property Text](/dotnet/api/microsoft.analysisservices.tabular.changedproperty.property#microsoft-analysisservices-tabular-changedproperty-property)     |
|ExternalModelRoleMember     |   MemberType      |    [RoleMemberType Enum](/dotnet/api/microsoft.analysisservices.tabular.rolemembertype)     |
|Any Custom JSON Property (for example, DataAccessOptions)     |   JSON Document      |    Json|
|LinguisticMetadata     |   Content      |    Json|

### Descriptions

TMDL provides first class support for descriptions. For model documentation purposes, best practice is to provide descriptions for each TOM object. TMDL treats descriptions as a special property with explicit syntax support. Following the examples from many other languages, descriptions are specified on top of each object declaration using triple-slash  (**///**) syntax.

No whitespace is allowed between the description block end and the object type token.

Descriptions can be split across multiple lines. The TMDL serializer breaks object descriptions into multiple lines to keep emitted document lines under the maximum length. The default maximum length is 80 characters.

```tmdl
/// Table Description
table Sales

    /// This is the Measure Description
    /// One more line
    measure 'Sales Amount'' = SUM(...)
        formatString: #,##0

```

### Partial declaration

TMDL doesn't force object declaration in the same document. It is, however, similar to [C# partial classes](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods) where it's possible split the object definition between multiple files. For example, you can declare a table definition in a [table].tmdl file and then have all the measures from all tables defined in a single [measures].tmdl file, as shown here:

```tmdl
table Sales

    measure 'Sales Amount' = SUM(…)
        formatString: $ #,##0

table Product

    measure CountOfProduct = COUNTROWS(…)

```

To avoid a parsing error, the same property can't be declared twice. For example, declaring  two measures with same name for the same table in two different TMDL documents results in an error.

### Object references

You can reference another TMDL object using the **ref** keyword followed by the object type and name. 

For example, if you serialize a Column object using the string serialization API, the outcome will be:

```tmdl
ref table Table1
	column Column1
		datatype: int64
		sourceColumn: Column1
```

#### Deterministic collection ordering

The **ref** keyword is also used to define and preserve the collection ordering on TOM <> TMDL roundtrips. It's particularly important to avoid source control diff's on TMDL objects that get serialized into individual files: Tables, Roles, Cultures and Perspectives. The **ref** keyword is used on the parent object TMDL file to declare the item ordering from TOM:

```tmdl

model Model

ref table Calendar
ref table Sales
ref table Product
ref table Customer
ref table About

ref culture en-US
ref culture pt-PT

ref role 'Stores Cluster 1'
ref role 'Stores Cluster 2'
```

The following rules are applied:

- During TMDL Deserialization:
  - Objects referenced in TMDL but with missing TMDL file, are ignored.
  - Objects not referenced but with existing TMDL file, are appended to the end of the collection.
- During TMDL Serialization:
  - All collection objects in TOM are referenced using the **ref** keyword.
  - Collections with only one item don't emit a ref.
  - Blank lines are not emitted between ref's if the same object type.

### Property value delimiters

There are only two delimiters/symbols to assign a property value:

- Equals (**=**)

  - Used at object declaration with [default property](#default-properties) (multi and single line)
  - Used at every [expression property](#expressions), for example, partition.expression
- Colon (**:**)
  - Used for every non-expression [property value](#object-properties). Including properties that hold model references.

### Indentation

TMDL uses strict whitespace indentation rules for denoting structure of the TOM hierarchy. A TMDL document uses a default single **tab** indentation rule.

Each object can have three levels of indentation:
- Level 1 - Object Declaration
    - Level 2 - Object Properties
        - Level 3 - Object property multi-line expressions

Within a TMDL document, indentation is applied in the following cases:

- Between an object section header and the object’s properties (table -> properties).

    ```tmdl
    table Sales
        isHidden
        lineageTag: 9a48bea0-e5fb-40fa-9e81-f61288e31a02
    ```

- Between an object and its child objects (table -> measures).

    ```tmdl
    table Sales
    
        measure 'Sales Amount' = SUMX(...)
    
        measure 'Total Quantity' = SUM(...)
    ```

- Between an object and its multi-line expressions (table -> measure -> expression).

    ```tmdl
    table Sales
    
        measure 'Sales Amount' = 
                var result = SUMX(...)
                return result
            formatString: $ #,##0
    ```

- Multi-line expressions must be indented one level deeper than object properties and the entire expression must be within that indentation level (see [expressions](#expressions)).

Database and direct child objects of Model don't need to be indented because they are implicitly assumed nested under the root Model or Database:

- model
- tables
- shared expressions
- roles
- cultures
- perspectives
- relationships
- data sources
- query groups
- model-level annotations
- model-level extended properties

Not following these indention rules generates a parsing error.

### Whitespace

TMDL by default applies the following rules to whitespace within property and expression values, when not enclosed within backticks (**```**) or double-quotes (**"**):

- On property values, leading and trailing whitespaces are trimmed.
- On expressions, whitespace lines at the end of expressions are dropped.
- Whitespace lines are trimmed to empty lines (no spaces/tabs).

### Casing

By default TMDL API on serialize/write use **camelCase**, applied to:

- Object types
- Keywords
- Enum values

On deserialize/read, TMDL API is case insensitive.

## Related content

Now that you have an understanding of TMDL, be sure to see [Get started with TMDL](tmdl-how-to.md) to learn how to get and deploy a TMDL model representation of a Power BI semantic model.
