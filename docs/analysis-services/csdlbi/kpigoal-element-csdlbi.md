---
title: "KpiGoal Element (CSDLBI) | Microsoft Docs"
description: Learn about the KpiGoal element, which provides a reference to the column that is used to define the goal for a key performance indicator (KPI).
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan

---
# KpiGoal Element (CSDLBI)

[!INCLUDE[csdl-archived](../includes/csdl-archived.md)]

  The KpiGoal element provides a reference to the column that is used to define the goal for a Key performance Indicator (KPI).  
  
 In CSDLBI, KPIs are based on measures, and the Measure element contains the formula (if any), while other metadata associated with the KPI are defined as part of the [KPI Element &#40;CSDLBI&#41;](kpi-element-csdlbi.md).  The Kpigoal element is a subtype of the Kpi element.  
  
## Elements and Attributes  
 The following table lists the attributes that define the KpiGoal element.  
  
|Name|Is Required|Description|  
|----------|-----------------|-----------------|  
|PropertyRef|Yes|A reference to the column that contains the KPI goal value.<br /><br /> The Kpigoal element must contain exactly one PropertyRef element.<br /><br /> See [PropertyRef Element &#40;CSDLBI&#41;](propertyref-element-csdlbi.md).|  
  
## Example Tabular
  
 The following sample, in CSDLBI version 1.1, shows a KPI from the Adventureworks sample model.  
  
```xml   
  
<Property Name="InternetCurrentSalesPerformance" Type="Double">  
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
  
 The following sample, in CSDLBI version 1.1, shows a KPI from the Contoso Operations cube.  
  
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
