---
title: "RelationshipEndVisualizationProperties Data Type (ASSL) | Microsoft Docs"
description: Learn about the RelationshipEndVisualizationProperties data type element in the Analysis Services Scripting Language (ASSL) schema.
ms.date: 10/31/2023
ms.service: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: kfollis
ms.reviewer: kfollis
author: kfollis

---
# RelationshipEndVisualizationProperties Data Type (ASSL)

  Defines a primitive data type that represents a relationship end in a relationship.  
  
## Syntax  
  
```xml  
  
<RelationshipEnd>  
   <FolderPosition>...</FolderPosition>  
   <ContextualNameRule>...</ContextualNameRule>  
   <DefaultDetailsPosition>...</DefaultDetailsPosition>  
   <DisplayKeyPosition>...</DisplayKeyPosition>  
   <CommonIdentifierPosition>...</CommonIdentifierPosition>  
   <IsDefaultMeasure>...</IsDefaultMeasure>  
   <IsDefaultImage>...</IsDefaultImage>  
   <SortPropertiesPosition>...</SortPropertiesPosition>  
</RelationshipEnd>  
```  
  
## Data Type Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Base data types|None|  
|Derived data types|None|  
  
## Data Type Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[RelationshipEnd](relationshipend-data-type-assl.md)|  
|Child elements|[FolderPosition](../../xmla/xml-elements-properties/folderposition-element-xml.md), [ContextualNameRule](../../xmla/xml-elements-properties/contextualnamerule-element-xml.md), [DefaultDetailsPosition](../../xmla/xml-elements-properties/defaultdetailsposition-element-xml.md), [DisplayKeyPosition](../../xmla/xml-elements-properties/displaykeyposition-element-xml.md), [CommonIdentifierPosition](../../xmla/xml-elements-properties/commonidentifierposition-element-xml.md), [IsDefaultMeasure](../../xmla/xml-elements-properties/isdefaultmeasure-element-xml.md), [IsDefaultImage](../../xmla/xml-elements-properties/isdefaultimage-element-xml.md), [SortPropertiesPosition](../../xmla/xml-elements-properties/sortpropertiesposition-element-xml.md)|  
|Derived elements||  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.RelationshipEnd>.  
  
  
