---
title: "DAX for multidimensional models in SQL Server Analysis Services | Microsoft Docs"
description: Learn how DAX works with multidimensional models.
ms.date: 09/17/2020
ms.prod: sql
ms.technology: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
---
# DAX for multidimensional models

[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

This article describes how Power BI uses DAX (Data Analysis Expressions) queries to report against multidimensional models in SQL Server Analysis Services.

Historically, reporting applications use MDX (Multidimensional Expressions) as a query language against multidimensional databases. MDX is optimized for common visual patterns like PivotTables in Excel and other reporting applications that target multidimensional business semantics. Beginning with SQL Server 2012 SP1, Analysis Services supports using both DAX and MDX against multidimensional and tabular models. DAX, however, was originally designed for tabular data models. While DAX is considered easier to use, it's also more focused on simpler data visualizations like tables, charts, and maps in reports and dashboards. **Power BI uses DAX to query both tabular and multidimensional models**.

Because DAX is primarily designed for tabular models, there are some interesting and useful mappings, and constraints, that must be understood when using DAX against multidimensional models.

## Compatibility

Power BI uses DAX to query Analysis Services multidimensional models in SQL Server 2016 and later Enterprise or Standard editions. SQL Server 2012 and SQL Server 2014 Enterprise or Business Intelligence editions are also supported, however, these versions are now out of mainstream support.

## Features

DAX is not a subset of MDX. DAX was initially designed to be similar to the Excel formula language. In tabular models, DAX is used against a relational data store comprised of tables and relationships. DAX is also used to create custom measures, calculated columns, and row-level security rules.

In addition to being a calculation language, DAX can also be used to execute queries. This article describes how DAX queries work against a multidimensional model.

### Interaction between MDX and DAX

DAX expressions are supported only within tabular models. You cannot use measures created by a DAX expression in a multidimensional model. A DAX query to a multidimensional model can reference a measure or other calculation that is defined in that model, but those calculations must be authored using the MDX language. DAX expressions cannot be used where an MDX expression is required and vice-versa, and some DAX functions, like PATH, are not applicable in multidimensional modeling at all.

### DAX Syntax

The syntax of DAX formulas is very similar to that of Excel formulas, and uses a combination of functions, operators, and values. To learn more about syntax for individual functions, see the [DAX function reference](/dax/dax-function-reference).

## Multidimensional to tabular object mapping

Analysis Services provides a tabular model metadata representation of a multidimensional model. Objects in a multidimensional models are then represented as tabular objects in Power BI. This mapping is exposed to Power BI by using the [DISCOVER_CSDL_METADATA](/openspecs/sql_server_protocols/ms-ssas/520fdc02-1b18-4534-a03b-4e97a26aa606) schema rowset.

### Object mapping

|Multidimensional object  |Tabular object  |
|---------|---------|
|Cube     | Model         |
|Cube dimension     | Table         |
|Dimension Attributes (Key(s), Name)      |  Column        |
|Measure group      |   Table       |
|Measure      |  Measure        |
|Measure without Measure group      |   In a table named Measures       |
|Measure group cube dimension relationship      |  Relationship        |
|Perspective      |  Perspective        |
|KPI    | KPI         |
|User/Parent-Child hierarchies     |  Hierarchy        |
|Display Folder     | Display Folder         |

### Measures, measure groups, and KPIs

Measure groups in a multidimensional cube are shown in the Power BI Fields list as tables with a calculator icon.

Measures within a measure group appear as measures. If there are calculated measures that do not have an associated measure group, they're be grouped under a special table called Measures.

To help simplify more complex multidimensional models, model authors can define a set of measures or KPIs in a cube to be located within a display folder. Power BI can show display folders and the measures and KPIs in them.

**Measures and KPIs in a measure group**

:::image type="content" source="media/dax-for-multidimensional-models/measuregroups-fieldlist.png" alt-text="Measures and KPIs in the Power BI Fields list":::

### Measures as variants

Measures in multidimensional models are variants. This means the measures are not strongly typed and can have different data types. For example, in the image below, the **Amount** measure in the Financial Reporting table by default is Currency data type, but also has a string value **NA** for the subtotal of **Statistical Accounts**, which is String data type. Power BI recognizes certain measures as variants and shows the correct values and formatting in the different visualizations.

**Measure as variant**

:::image type="content" source="media/dax-for-multidimensional-models/daxmd-nonaggrattrib.gif" alt-text="Measure as a variant":::

### Implicit measures

Tabular models provide users the ability to create implicit measures such as count, sum, or average on fields. For multidimensional models, because dimension attribute data is stored is stored differently, querying implicit measures can take a long time. Because of this, implicit measures against multidimensional models are not available in Power BI.

## Dimensions, attributes, and hierarchies

Cube dimensions are exposed as tables in tabular metadata. In the Power BI Fields list, dimension attributes are shown as columns within display folders. The dimension attributes that have the **AttributeHierarchyEnabled** property set to **False**; for example: Birth Date attribute in Customer dimension, or AttributeHierarchyVisible property set to false will not appear in the Power BI Fields list. Multi-level hierarchies or user hierarchies; for example Customer Geography in the Customer dimension, are exposed as hierarchies in the Power BI Fields list. Hidden UnknownMembers of a dimension attribute are exposed in DAX queries and in Power BI.

**Dimension, attributes, and hierarchies in SQL Server Data Tools (SSDT) and Power BI Fields list**

:::image type="content" source="media/dax-for-multidimensional-models/dimensions_attributes_hierarchies.png" alt-text="Dimensions, attributes, hierarchies in SSDT and Power BI Fields list":::

### Dimension attribute type

Multidimensional models support associating dimension attributes with specific dimension attribute types. The image below shows the **Geography** dimension where City, State-Province, Country and Postal Code dimension attributes have geography types associated with them. These are exposed in the tabular metadata. Power BI recognizes the metadata enabling users to create map visualizations. This is indicated by the map icon next to the City, Country, Postal Code and State-Province columns in the Geography table in the Power BI Fields List.

**Geography dimension in SSDT and Power BI Fields list**

:::image type="content" source="media/dax-for-multidimensional-models/dimension-attribute-type.png" alt-text="Dimension attribute type in SSDT and Power BI Fields list":::

### Dimension calculated members

Multidimensional models support calculated members for child of **All** with a single real member. Additional constraints while exposing this type of calculated member are:

- Must be a single real member when the dimension has more than one attribute.
- An attribute containing calculated members cannot be the key attribute of the dimension unless it is the only attribute.
- An attribute containing calculated members cannot be a parent-child attribute.

Calculated members of user hierarchies are not exposed in Power BI, however, users are still able to connect to a cube containing calculated members on user hierarchies.

### Default members

Multidimensional models support default members for dimension attributes. The default member is used by Analysis Services when aggregating data for a query. The default member of a dimension attribute is exposed as default value or filter for the corresponding column in the tabular metadata.

Power BI behaves much the same as Excel PivotTables when attributes are applied. When a user adds a column to a Power BI visualization (table, matrix, or chart) that contains a default value, the default value will not be applied and all available values are shown. If the user adds the column to Filters, the default value is applied.

### Dimension security

Multidimensional models support dimension and cell level security through roles. A user connecting to a cube by using Power BI is authenticated and evaluated for appropriate permissions defined by roles the user belongs to. When dimension security is applied, the respective dimension members are not be seen by the user in Power BI. However, if a user has a cell security permission defined where certain cells are restricted, then that user cannot connect to the cube with Power BI. In some cases, users can see aggregate data when portions of that data are calculated from secured data.

### Non-aggregatable attributes/hierarchies

In multidimensional models, attributes of a dimension can have the **IsAggregatable** property set to **False**. This means the model author has specified reporting applications should not aggregate the data across hierarchies (attribute or multi-level) when they query the data. In Power BI, this dimension attribute is exposed as a column for which subtotals are not available. In the following image, you see an example of a non-aggregatable hierarchy, Accounts. The top-most level of the Accounts parent-child hierarchy is non-aggregatable while other levels are aggregatable. In a matrix visualization of the Accounts hierarchy (first two levels), you see subtotals for **Account Level 02** but not for the top-most level, **Account Level 01**.

**Non-aggregatable hierarchy in Power BI**

:::image type="content" source="media/dax-for-multidimensional-models/daxmd-nonaggrattrib.gif" alt-text="Measure as a variant":::

## Images

Power BI provides the ability to render images. In multidimensional models, one of the ways you can provide images to be shown in Power BI is to expose columns containing URLs (Uniform Resource Locator) of the images. Analysis Services supports tagging dimension attributes as type **ImageURL**. This data type is then provided to Power BI in the tabular metadata. Power BI can then download and display the images specified in the URLs within visualizations.

**ImageURL dimension attribute type in SSDT**

:::image type="content" source="media/dax-for-multidimensional-models/daxmd-dimattribute-properties.gif" alt-text="ImageURL dimension in SSDT":::

## Parent-child hierarchies

Multidimensional models support parent-child hierarchies, which are exposed as a hierarchy in tabular metadata. Each level of the parent-child hierarchy is exposed as a hidden column. The key attribute of the parent-child dimension is not exposed in the tabular metadata.

**Parent-child hierarchies in SSDT and Power BI Fields list**

:::image type="content" source="media/dax-for-multidimensional-models/parent-child-hierarchies.png" alt-text="Parent-child hierarchies in SSDT and Power BI Fields list":::

## Perspectives and translations

Perspectives are views of cubes where only certain dimensions or measure groups are visible in client tools. You can specify a perspective name as a value to the **Cube** connection string property. For example, in the following connection string, **'Direct Sales'** is a perspective in the multidimensional model:

`Data Source=localhost;Initial Catalog=AdventureWorksDW-MD;Cube='Direct Sales'`

Cubes can have metadata and data translations specified for various languages within the model. In order to see the translations (data and metadata) an application can add the optional **Locale Identifier** property to the connection string, for example:

`Data Source=localhost;Initial Catalog=AdventureWorksDW-MD;Cube='Adventure Works'; Locale Identifier=3084`

When Power BI Desktop connects to a multidimensional model, it automatically passes the current user locale identified to the server. However, this does not occur for a report that is published to the Power BI service.

## Unsupported features

**Cell level security** - is not supported in Power BI reports.

**Actions** - are not supported in Power BI reports or in DAX queries against a multidimensional model.

**Named sets** - in multidimensional models, are not supported in Power BI or in DAX queries against a multidimensional model.

> [!NOTE]
> Unsupported Actions and Named sets do not prevent users from connecting to and exploring multidimensional models when using Power BI.

## CSDLBI Annotations

Multidimensional cube metadata is exposed as an Entity Data Model (EDM) based conceptual model by Conceptual Schema Definition Language with Business Intelligence annotations (CSDLBI).

Multidimensional metadata is represented as a tabular model namespace in a CSDLBI document, or CSDL out, when a DISCOVER_CSDL_METADATA request is sent to the Analysis Services instance.

**Example: DISCOVER_CSDL_METADATA request** 

```xml
<Envelopexmlns="http://schemas.xmlsoap.org/soap/envelope/">
   <Body>
      <Discoverxmlns="urn:schemas-microsoft-com:xml-analysis">
         <RequestType>DISCOVER_CSDL_METADATA</RequestType>
         <Restrictions>
            <RestrictionList>
              <CATALOG_NAME>"catalogname"<CATALOG_NAME>
            </RestrictionList>
         </Restrictions>
         <Properties>
            <PropertyList>
            </PropertyList>
         </Properties>
      </Discover>
   </Body>
</Envelope>
```

The DISCOVER_CSDL_METADATA request has the following restrictions:

|Name  |Required  |Description  |
|---------|---------|---------|
|CATALOG_NAME     |    Yes     |    The catalog\database name.      |
|PERSPECTIVE_NAME     |    Yes, if the cube contains more than one perspective. Optional if there is only one cube or there is a default perspective.      |   The cube name or perspective name in the multidimensional database.       |
|VERSION      |   Yes      |    CSDL version requested by client. Multidimensional features and constructs are supported in version 2.0.      |

The return CSDL out document represents the model as a namespace, containing entities, associations, and properties.

To learn more about CSDLBI annotations, see [Technical Reference for BI Annotations to CSDL](../csdlbi/technical-reference-for-bi-annotations-to-csdl.md), and [[MS-CSDLBI]: Conceptual Schema Definitions File Format with Business Intelligence Annotations](/openspecs/sql_data_portability/ms-csdlbi/336647b0-95bf-4375-962d-4024c4554faa).

## SuperDAXMD

With each release of SQL Server Analysis Services, improvements support new and existing DAX functions and capabilities. In SQL Server 2019 CU5, a class of DAX functions first introduced for tabular models informally known as *SuperDAX* are now enabled for multidimensional models.

While some existing DAX query patterns may need to be redesigned, SuperDAX functions provide significant improvements to query performance. Modern DAX query patterns using SuperDAX for multidimensional models provide a strong incentive for organizations using Power BI to upgrade their multidimensional data source servers to SQL Server 2019 with CU5. To learn more, see [SuperDAX for multidimensional models](../what-s-new-in-sql-server-analysis-services.md#superdax-for-multidimensional-models-superdaxmd).

## See also

[DAX reference](/dax/)