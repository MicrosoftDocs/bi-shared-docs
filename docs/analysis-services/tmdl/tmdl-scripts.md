---
title: "TMDL scripts"
description: Learn how to use TMDL scripts.
ms.date: 01/14/2025
ms.service: analysis-services
ms.custom: tmdl
ms.topic: reference
ms.author: davidi
ms.reviewer: rromano
author: davidiseminger
---

# TMDL scripts

TMDL scripts enable you to apply an action to a semantic model, which could be a change or operation. A TMDL script has two parts:

* A *command*, which is required and should be declared at the top of the TMDL script.
* One or more *semantic model objects* using TMDL language definition or reference.

Syntax:


```tmdl

<TMDL Command name>
  <TMDL object>
  [<TMDL object>]

```



## CreateOrReplace command

Creates or replaces the specified semantic model objects and all the descendants. Existing objects are replaced with a new definition.

The order of TMDL objects inside the *createOrReplace* command is not important. 

The semantics of TMDL language are applied to objects within the *createOrReplace* command. For example, it's possible to split the object definition into multiple segments, however the same property can't be declared more than once. You can [learn more about the TMDL language](tmdl-overview.md).


## Example

Create or replace the measure *# Products (with Sales)* from the table *Sales*and the full definition of the table *Product*:



```tmdl
createOrReplace

  ref table Sales
    measure '# Products (with Sales)' = DISTINCTCOUNT('Sales'[ProductKey])
        formatString: #,##0
    
  table Product

    measure '# Products' = COUNTROWS('Product')
        formatString: #,##0

    column Product
        dataType: string
        isDefaultLabel
        summarizeBy: none
        sourceColumn: Product

    column Category
        dataType: string
        summarizeBy: none
        sourceColumn: Category

    partition Product-partition = m
        mode: import
        source =
                let
                    Source = #"RAW-Product",
                    #"Renamed Columns" = Table.RenameColumns(Source,{{"Product Name", "Product"}})
                in
                    #"Renamed Columns"
```

## Considerations and limitations

Only one command verb per script execution is supported.

## Related content

The following articles describe more about TMDL and its uses.

* [Get started with TMDL](/analysis-services/tmdl/tmdl-how-to)
* [Tabular Model Definition Language (TMDL)](/analysis-services/tmdl/tmdl-overview)
* [Power BI Desktop projects (preview)](/power-bi/developer/projects/projects-overview)
* [Power BI Desktop project semantic model folder](/power-bi/developer/projects/projects-dataset)


