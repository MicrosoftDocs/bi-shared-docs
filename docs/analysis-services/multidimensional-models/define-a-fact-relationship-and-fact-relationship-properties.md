---
title: "Define a Fact Relationship and Fact Relationship Properties | Microsoft Docs"
description: Learn how to view or edit a fact dimension relationship on the Dimension Usage tab of Cube Designer.
ms.date: 05/02/2018
ms.service: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual

---
# Define a Fact Relationship and Fact Relationship Properties
[!INCLUDE[appliesto-sqlas](../includes/appliesto-sqlas.md)]
  When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] will try to detect if a fact dimension relationship exists and then set the dimension usage setting to **Fact**. You can view or edit a fact dimension relationship on the **Dimension Usage** tab of Cube Designer. The fact relationship between a dimension and a measure group has the following constraints:  
  
-   A cube dimension can have only one fact relationship to a particular measure group.  
  
-   A cube dimension can have separate fact relationships to multiple measure groups.  
  
-   The granularity attribute for the relationship must be the key attribute (such as Transaction Number) for the dimension. This creates a one-to-one relationship between the dimension and facts in the fact table.  
  
  
