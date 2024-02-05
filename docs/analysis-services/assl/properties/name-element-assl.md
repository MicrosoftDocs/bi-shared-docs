---
title: "Name Element (ASSL) | Microsoft Docs"
description: Learn about the Name property element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 7/25/2018
ms.service: analysis-services
ms.custom: assl
ms.reviewer: kfollis

ms.topic: reference
author: minewiskan
ms.author: kfollis

---
# Name Element (ASSL)

  Contains the name of the parent element.  
  
## Syntax  
  
```xml  
  
<Action> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Name>...</Name>  
   ...  
</Action>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (up to 100 characters)|  
|Default value|Varies|  
|Cardinality|1-1: Required element that occurs once and only once|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Action](../objects/action-element-assl.md), [Aggregation](../objects/aggregation-element-assl.md), [AggregationDesign](../objects/aggregationdesign-element-assl.md), [AlgorithmParameter](../objects/algorithmparameter-element-assl.md), [Annotation](../objects/annotation-element-assl.md), [Assembly](../objects/assembly-element-assl.md), [ClrAssemblyFile](../data-type/clrassemblyfile-data-type-assl.md), [Cube](../objects/cube-element-assl.md), [CubeDimension](../data-type/cubedimension-data-type-assl.md), [CubeHierarchy](../data-type/cubehierarchy-data-type-assl.md), [Database](../objects/database-element-assl.md), [DataSource](../objects/datasource-element-assl.md), [DataSourceView](../objects/datasourceview-element-assl.md), [Dimension](../objects/dimension-element-assl.md), [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md), [Group](../objects/group-element-assl.md), [Hierarchy](../objects/hierarchy-element-assl.md), [Kpi](../objects/kpi-element-assl.md), [Level](../objects/level-element-assl.md), [MdxScript](../objects/mdxscript-element-assl.md), [Measure](../objects/measure-element-assl.md), [MeasureGroup](../objects/measuregroup-element-assl.md), [MemberProperty](../objects/attributerelationship-element-assl.md), [MiningModel](../objects/miningmodel-element-assl.md), [MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md), [MiningStructure](../objects/miningstructure-element-assl.md), [MiningStructureColumn](../data-type/miningstructurecolumn-data-type-assl.md), [Partition](../objects/partition-element-assl.md), [Permission](../data-type/permission-data-type-assl.md), [Perspective](../objects/perspective-element-assl.md), [PerspectiveCalculation](../data-type/perspectivecalculation-data-type-assl.md), [ReportFormatParameter](../objects/reportformatparameter-element-asl.md), [ReportParameter](../objects/reportparameter-element-assl.md), [Role](../objects/role-element-assl.md), [Server](../objects/server-element-assl.md), [ServerProperty](../objects/serverproperty-element-assl.md), [Trace](../objects/trace-element-assl.md)|  
|Child elements|None|  
  
## Remarks  
 Every element that is used to define an object (an instance of Analysis Services, a hierarchy, an attribute, and so on) has a **Name** element as a property. The value of a **Name** element has the following restrictions:  
  
-   The value cannot contain leading or trailing spaces. If leading or trailing spaces are included in the value of a **Name** element, those spaces will be implicitly removed byAnalysis Services.  
  
-   The value should not contain control characters. The presence of control characters in a name is strongly discouraged and can sometimes result in XML validation errors.  
  
     For objects created using the **GetNewName** method in SQL Server, AMO checks for and subsequently removes any control characters, leading spaces, or trailing spaces in the name. For this reason, using **GetNewName** is the recommended approach for setting object names.  
  
     However, if you set the **Name** property directly, the same validation checks are not performed, possibly resulting in XML validation errors. Whether an error actually occurs depends on which control character appears in the name.  
  
     Although control characters should never be used in an object name, Analysis Services does not expressly prevent them. Previous releases of Analysis Services sometimes accepted control characters in an object name. For this reason, SQL Server 2016 Analysis Services and later will ignore control characters in an object name to avoid breaking older solutions.  
  
-   The following reserved values cannot be used:  
  
    -   AUX  
  
    -   CLOCK$  
  
    -   COM1 through COM9 (COM1, COM2, COM3, and so on)  
  
    -   CON  
  
    -   LPT1 through LPT9 (LPT1, LPT2, LPT3, and so on)  
  
    -   NUL  
  
    -   PRN  
  
The following table lists additional characters that cannot be used within the value of a **Name** element, depending on the parent element.  
  
|Parent element|Invalid Characters|  
|--------------------|------------------------|  
|[Server](../objects/server-element-assl.md)|The name must follow the rules for  Windows computer names. IP addresses are not valid.|  
|[DataSource](../objects/datasource-element-assl.md)|`:/\\*&#124;?"()[]{}<>` \`|  
|[Level](../objects/level-element-assl.md), [Attribute Element](../objects/attribute-element-assl.md)|`.,;':/\\*&#124;?"&%$!+=[]{}<>` \`|  
|All other parent elements|`.,;':/\\*&#124;?"&%$!+=()[]{}<>` \`|  
  
## See Also

 [ID Element &#40;ASSL&#41;](id-element-assl.md)   
 [Properties &#40;ASSL&#41;](properties-assl.md)  
  
  
