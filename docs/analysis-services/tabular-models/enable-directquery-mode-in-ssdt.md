---
title: "Enable in Analysis Services DirectQuery mode in Visual Studio | Microsoft Docs"
description: Describes how to enable DirectQuery mode for tabular models by using Tabular model designer in Visual Studio.
ms.date: 08/27/2020
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---
# Enable DirectQuery mode in Visual Studio

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

This article describes how to enable DirectQuery mode for a tabular model project in Tabular model designer in Visual Studio.  
  
When you enable DirectQuery mode:

- Features that are incompatible with DirectQuery mode are disabled.  
- The existing model is validated. Warnings are displayed if features are incompatible with DirectQuery mode.  
- If data was previously imported prior to enabling DirectQuery mode, the working model's cache is emptied.  
  
## Enable DirectQuery
  
In Visual Studio, in the **Properties** pane for the **Model.bim** file, change the property, **DirectQuery Mode**, to **On**.  

![Enable DirectQuery mode in Visual Studio](../../analysis-services/tabular-models/media/enable-directquery-mode-in-ssdt.png)
  
If your model already has a connection to a data source and existing data, you'll be prompted to enter database credentials used to connect to the relational database. Any data already existing within the model will be removed from the in-memory cache.  
  
If your model is partially or fully complete prior to enabling DirectQuery mode, you might get errors about incompatible features. In Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being switched to DirectQuery mode.

> [!NOTE]
> Disregard  **Table \<TableName> does not contain a sample partition; to use data in SSDT please add a sample partition** warnings. Currently, the **Set as Sample** feature is not supported. To learn more, see [Adding sample data to a DirectQuery model project](directquery-mode-ssas-tabular.md#adding-sample-data-to-a-directquery-model-project).

## See also

[Enable DirectQuery mode in SSMS](../../analysis-services/tabular-models/enable-directquery-mode-in-ssms.md)  
[Add sample data to a DirectQuery model in design mode](./directquery-mode-ssas-tabular.md)