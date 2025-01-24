---
title: "Lineage tags for Power BI semantic models"
description: Add a lineage tag for Power BI semantic models.
ms.date: 01/06/2025
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: davidi
ms.reviewer: davidi
author: davidiseminger

---
# Lineage tags for Power BI semantic models

You can use [lineage tags](/dotnet/api/microsoft.analysisservices.tabular.imetadataobjectwithlineage.lineagetag) in semantic model objects to enable stable identification of such objects across different semantic models. Using lineage tags enables Power BI features such as [composite models](/power-bi/transform-model/desktop-composite-models) to maintain their binding to referenced tables or columns (by use of [SourceLineageTag](/dotnet/api/microsoft.analysisservices.tabular.imetadataobjectwithlineage.sourcelineagetag)), even if the source semantic model object is renamed. 

Lineage tags must be unique within their scope; for instance, two tables in the same semantic model can't have the same lineage tag. Power BI Desktop typically assigns a GUID for each semantic model object requiring lineage, but such assignment is not mandatory and lineage tags can be changed to any other string format.

> [!IMPORTANT]
> If semantic model objects don't have a lineage tag, Power BI defaults to using the object name, which can lead to the loss of customizations if the object is renamed.

## Tracking user customizations to semantic models

Semantic models can include objects and properties derived from other models or data sources. For example, when creating a [composite model on Power BI semantic models](/power-bi/transform-model/desktop-composite-models#composite-models-on-power-bi-semantic-models-and-analysis-services), the table and column names, data types, format strings, and other properties originate from the source model. 

When customizing properties or removing objects in the model that have been synced from the data source, Power BI expects the [changedProperties property](/dotnet/api/microsoft.analysisservices.tabular.table.changedproperties) and *PBI_RemovedChildren* annotation to be set to indicate a user customization so that the customizations are maintained during the next schema synchronization with the data source. 

The following objects/properties synchronize with the data source and require you to declare both any modified properties and object removals: 


|Scenario  |Objects  |Property customization  |Removal customization  |
|---------|---------|---------|---------|
|Import / DirectQuery  |Tables, Columns, Relationships  |Name, DataType  |Relationships <sup>[1](#sameas)</sup>  |
|Composite     |Tables, Columns, Relationships, Measures, Hierarchies, Levels           |Name, DataType, IsHidden, FormatString, Description, SummarizeBy, DataCategory, SortByColumn, GroupByColumns, DisplayFolder, IsNullable           |All tables in the remote model not included in the local model     |
|DirectLake      |Tables, Columns           |Name, DataType           |All tables in the Lakehouse not included in the model          |

<a name="sameas">[1]</a> Power BI automatically creates relationships based on primary and foreign key information from the data source. If users remove those relationships, Power BI keeps track of the changes to prevent re-adding them during future schema synchronization.

### The ChangedProperties collection

The *ChangedProperties* collection enables you to specify which object property values have been modified, indicating that those values may no longer be synchronized with the source.  

For example, when creating a composite model on Power BI semantic models, the column names originate from the source model. If you rename a column in your local model, you need to specify the *Name* property as a changed property.  

In the following example, the *ProductID* column from the source model was renamed to *ProductKey*: 


```TMDL
table Products 

    column ProductKey 
        dataType: int64          
        lineageTag: 9636345e-0328-43fb-acd3-e7894734d08a 
        sourceLineageTag: 6890686b-4899-4916-9ec2-2e8ff5a05eb7               
        sourceColumn: ProductID 

        changedProperty = Name
```

### The PBI_RemovedChildren annotation

The *PBI_RemovedChildren* annotation is a model annotation declared on the parent object of the removed item that declares the user's intent to exclude an object from the local object. For example, when constructing a composite model you [can choose which tables to load](/power-bi/transform-model/desktop-composite-models#loading-a-subset-of-tables-from-a-power-bi-semantic-model-or-analysis-services-model), and all the non-selected tables are included in the *PBI_RemovedChildren* annotation stored in the *NamedExpression* of the data source. In Import and DirectQuery models, the annotation is stored within the model to keep track of relationship removals.

Not declaring this annotation causes semantic model objects to be retrieved during schema synchronization with the source.  

In the following example a table is removed from the composite model. The lineage tag of the source model table is used instead of its name to ensure a stable identification: 

```TMDL
expression 'DirectQuery to AS - AdventureWorks' = 
        let 
            Source = AnalysisServices.Database("[XMLA Endpoint]"), 
            Cubes = Table.Combine(Source[Data]), 
            Cube = Cubes{[Id="Model", Kind="Cube"]}[Data] 
        in 
            Cube 

    annotation PBI_RemovedChildren = [{"remoteItemId":{"analysisServicesObject":{"sourceName":null,"sourceLineageTag":"8e47b52e-1c1a-4029-b6cc-25200d213fcf"}},"objectType":"Table"}]
```

## Considerations and limitations

* For Import/DirectQuery models, the *changedProperty* is required only when the change cannot be folded into the M query of the table, such as in DirectQuery tables utilizing a native query. 
* For DirectLake models, the *sourceLineageTag* must be the name of the table/column in the Lakehouse/data warehouse. 


## Next step

The following articles contain useful additional information:

* [Model write support with the XMLA endpoint](/fabric/get-started/direct-lake-develop#model-write-support-with-the-xmla-endpoint)
* [XMLA modifications and composite models](/power-bi/transform-model/desktop-composite-models#xmla-modifications-and-composite-models)
