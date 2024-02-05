---
title: "Analysis Services DAX properties | Microsoft Docs"
description: Learn about the DAX settings used to control certain query behaviors in Analysis Services.
ms.date: 07/21/2022
ms.service: analysis-services
ms.custom: 
ms.topic: conceptual
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis
monikerRange: "asallproducts-allversions || azure-analysis-services-current || power-bi-premium-current || >= sql-analysis-services-2016"
---

# DAX properties

[!INCLUDE[appliesto-sqlas-all-aas-pbip](../includes/appliesto-sqlas-all-aas-pbip.md)]

Analysis Services includes advanced properties that determine DAX query response. For very large rowsets, such as those returned by a DAX query in DirectQuery models, the default of one million rows could be insufficient. To increase the upper limit, specify the **MaxIntermediateRowSize** setting. You'll know whether the limit needs adjusting if you get this error: "The result set of a query to external data source has exceeded the maximum allowed size of '1000000' rows."

## Properties

Setting |Value |Description
--------|-------|-----------
MaxIntermediateRowsetSize | 1000000 | Maximum number of rows returned in a DAX query. For SSAS, manually add this entry to the msmdsrv.ini file and increase the value if the default is too low.
PredicateCheckSpoolCardinalityThreshold| 5000 | Does not apply to Power BI. An advanced property that you should not change, except under the guidance of Microsoft support.

::: moniker range="asallproducts-allversions || >= sql-analysis-services-2016"

For SSAS, you must manually add the entire element to the DAX section of the configuration file. The setting isn't present in the file until you add it.

## Configuration snippet (msmdsrv.ini)

```json
<ConfigurationSettings>
. . .
<DAX>
  <PredicateCheckSpoolCardinalityThreshold>5000
  </PredicateCheckSpoolCardinalityThreshold>
  <DQ>
     <MaxIntermediateRowsetSize>1000000
     </MaxIntermediateRowsetSize>
  </DQ>
</DAX>
. . .
```

::: moniker-end

To learn more about other server properties and how to set them, see [Server properties in Analysis Services](../../analysis-services/server-properties/server-properties-in-analysis-services.md).
