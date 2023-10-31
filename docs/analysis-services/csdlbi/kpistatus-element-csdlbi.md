---
title: "KpiStatus Element (CSDLBI) | Microsoft Docs"
description: Learn about the KpiStatus element, which defines a reference to the column that contains the value used as the status indicator in a KPI.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# KpiStatus Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The KpiStatus element defines a reference to the column that contains the value used as the status indicator in a Key Performance Indicator (KPI).  
  
## Elements and Attributes  
 The following table lists the elements and attributes that define the KpiStatus element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|PropertyRef|Yes|A reference to a column that contains the value used as the status indicator in a KPI.<br /><br /> This element MUST contain exactly one column reference, as defined by the TPropertyRefcomplex type.|  
  
## Example Tabular
  
 The following sample, in CSDLBI version 1.1, shows a KPI from the AdventureWorks tabular model sample. The KpiStatus element refers to a column (represented as a PropertyRef) that contains the value.  
  
```xml   
  
<Property Name="InternetCurrSalesPerf" Type="Double">  
   <bi:Measure>  
     <bi:Kpi StatusGraphic="Three Stars Colored">  
       <bi:KpiGoal>  
         <bi:PropertyRef Name="v_InternetCurrSalesPerf_Goal" />  
       </bi:KpiGoal>  
       <bi:KpiStatus>  
         <bi:PropertyRef Name="v_InternetCurrSalesPerf_Status" />  
       </bi:KpiStatus>  
     </bi:Kpi>  
   </bi:Measure>  
</Property>  
  
```  
  
## Example Multidimensional
  
 The following sample, in CSDLBI version 1.1, shows a KPI from the Contoso Operations cube. The KpiStatus element references a measure that calculates the value for the KPI status.  
  
```xml   
<bi:Measure   
       Caption="Sum of SalesAmount"   
       ReferenceName="Sum of SalesAmount"   
       FormatString="\$#,0.00;(\$#,0.00);\$#,0.00">  
  
    <bi:Kpi   
       StatusGraphic="Three Circles Colored">  
  
      <bi:KpiGoal>  
         <bi:PropertyRef   
          Name="v_Sum_of_SalesAmount_Goal" />  
       </bi:KpiGoal>  
  
       <bi:KpiStatus>  
          <bi:PropertyRef   
          Name="v_Sum_of_SalesAmount_Status" />  
        </bi:KpiStatus>  
  
       </bi:Kpi>  
</bi:Measure>  
  
```  