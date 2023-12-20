---
title: "Object Definitions in Tabular Model Definition Language (TMDL) | Microsoft Docs"
description: See a list of the major TMDL schema objects.
ms.date: 12/20/2023
ms.service: analysis-services
ms.custom: tmdl
ms.topic: reference
ms.author: monaberdugo
ms.reviewer: rromano
author: mberdugo
---

# TMDL Reference - Objects overview

[!INCLUDE[appliesto-sql2016-later-aas-pbip](../includes/appliesto-sql2016-later-aas-pbip.md)]

All **TMDL** objects have an exact match with their **Tabular Object Model (TOM)** properties, except for [Translations](#translations-in-tmdl) and [Role members](#role-members-in-tmdl).

For example, look at the following TMDL calculated column representation:

```tmdl

table Calendar

  column 'Date (Year-Month)' = DATE([Year], [Month],1)
    dataType: dateTime
    formatString = mmm yyyy
    lineageTag: 0e65a7a5-6c15-437d-8333-10653d8d673f
    summarizeBy: none

    annotation SummarizationSetBy = automatic
```

Each of the preceding TMDL properties maps to the [CalculatedTableColumn](/dotnet/api/microsoft.analysisservices.tabular.calculatedtablecolumn?view=analysisservices-dotnet) class properties as follows:

- [expression](/dotnet/api/microsoft.analysisservices.tabular.calculatedcolumn.expression?view=analysisservices-dotnet#microsoft-analysisservices-tabular-calculatedcolumn-expression) - Default Property
- [dataType](/dotnet/api/microsoft.analysisservices.tabular.column.datatype?view=analysisservices-dotnet#microsoft-analysisservices-tabular-column-datatype)
- [formatString](/dotnet/api/microsoft.analysisservices.tabular.column.formatstring?view=analysisservices-dotnet#microsoft-analysisservices-tabular-column-formatstring)
- [lineageTag](/dotnet/api/microsoft.analysisservices.tabular.column.lineagetag?view=analysisservices-dotnet#microsoft-analysisservices-tabular-column-lineagetag)
- [summarizeBy](/dotnet/api/microsoft.analysisservices.tabular.column.summarizeby?view=analysisservices-dotnet#microsoft-analysisservices-tabular-column-summarizeby)

## Translations in TMDL

In TOM, translations are represented as a collection of [ObjectTranslation](/dotnet/api/microsoft.analysisservices.tabular.objecttranslation?view=analysisservices-dotnet) objects. For optimal interaction and readability, TMDL breaks the principle of alignment with the TOM object tree and replicates the model hierarchy underneath each culture as virtual TMDL properties.

For each object, translations can be added for the following properties:

|Property  |Description  |
|---------|---------|
|caption |Translated table/column/measure/... title that appears in any client application supporting visualizations of a Tabular model.|
|description |Translated description appears as model information.|
|displayFolder|translated column/measure/hierarchy display folder used by client applications to organize content. |

The following code example is a TMDL translation for Portuguese culture (pt-PT):

```tmdl
culture pt-PT
 translations
  model Model
   caption: Modelo
   description: Modelo
   table Calendar
    caption: Calendário
   table Sales
    caption: Vendas
    measure 'Sales Amount'
     caption: Total de Vendas
     displayFolder: Métricas Base
    measure 'Sales Amount (LY)'
     caption: Total Vendas (Ano Anterior)
     displayFolder: Métricas Base
    measure 'Sales Amount (YTD, LY)'
     displayFolder: Métricas Base
   table Product
    caption: Produto
    description: Tabela de Produto
    column Product
     caption: Produto
     description: Coluna de Produto
    column ProductKey
     caption: Chave de Produto
    column Weight
     caption: Peso
    hierarchy 'Product Hierarchy'
     caption: Hierarquia de Produto
   table Customer
    caption: Cliente
    column Address
     caption: Morada
   table Store
    caption: Loja
    column StoreKey
     caption: Código de Loja

 linguisticMetadata =   
   {
     ...
   }

```

## Role Members in TMDL

Role members could number in the hundreds or thousands, so serializing each member as a separate object using its native TOM representation ([WindowsModelRoleMember](/dotnet/api/microsoft.analysisservices.tabular.windowsmodelrolemember?view=analysisservices-dotnet) or [ExternalModelRoleMember](/dotnet/api/microsoft.analysisservices.tabular.externalmodelrolemember?view=analysisservices-dotnet)) would be unreadable. To optimize for interaction and readability, TMDL breaks the principle of alignment with TOM object tree, and optimizes role members representation for the most common scenario: Microsoft Entra ID (formerly known as Azure AD) and Windows Identity.

The following rules are applied:

- Member ID isn't serialized and assumes the same value as name
- Blank lines between members aren't emitted
- Members are emitted in the end after permissions

Default property of the member determines the member type:

|Default Property Value  |Description  |
|---------|---------|
|user | ExternalModelRoleMember - IdentityProvider = AzureAD, RoleMemberType = User|
|group | ExternalModelRoleMember  - IdentityProvider = AzureAD, RoleMemberType = Group|
|auto | ExternalModelRoleMember  - IdentityProvider = AzureAD, RoleMemberType = Auto|
|activeDirectory | WindowsModelRoleMember|

The following code example is a TMDL role with `ExternalModelRoleMembers` members:

```tmdl

role 'StoreRole'
 modelPermission: read

 tablePermission Store = 'Store'[Store Code] IN {"1","2","4"}
 
 member 'user1@company.com'
 member 'group@domain.com' = group
 member 'user2@company.com' = auto
 member user1FromCustomProvider
  identityProvider = customProviderName
 member group1FromCustomProvider
  identityProvider = customProviderName
```

The following code example is a TMDL role with `WindowsModelRoleMember` members:

```tmdl

role 'StoreRole'
 modelPermission: read

 tablePermission Store = 'Store'[Store Code] IN {"1","2","4"}
 
 member company\user1 = activeDirectory
 member company\group = activeDirectory
```
