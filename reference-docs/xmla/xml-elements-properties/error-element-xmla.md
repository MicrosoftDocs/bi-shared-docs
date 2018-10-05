---
title: "Error Element (XMLA) | Microsoft Docs"
ms.date: 07/24/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Error Element (XMLA)

  Contains information about an error returned by an instance of Analysis Services.  
  
## Syntax  
  
```xml  
  
<Message>  
   <Error   
      ErrorCode="unsignedint"   
      Severity="string"   
      Description="string"  
      Source="string"  
      HelpFile="string"  
   />  
</Message>  
<!-- or -->  
<Cell><!-- or row -->  
   <!-- A child element -->  
      <Error xmlns="urn:schemas-microsoft-com:xml-analysis:exception"  
         < ErrorCode>...</ErrorCode>  
         < Description>...</Description>  
         < Source>...</Source>  
         < HelpFile>...</HelpFile>  
      </Error>  
   <!-- /A child element -- >  
</Cell>  
```  
  
## Element characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Message](../xml-elements-properties/message-element-xmla.md)|  
|Child elements|See the table below.|  
  
|Ancestor|Child elements|  
|--------------|--------------------|  
|[Message](../xml-elements-properties/message-element-xmla.md)|None|  
|[Cell](../xml-elements-properties/cell-element-mddataset-xmla.md), [row](../xml-elements-properties/message-element-xmla.md)|[Description](../xml-elements-properties/description-element-xmla.md), [ErrorCode](../xml-elements-properties/errorcode-element-xmla.md), [HelpFile](../xml-elements-properties/helpfile-element-xmla.md), [Source](../xml-elements-properties/source-element-error-xmla.md)|  
  
## Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|ErrorCode|Required **UnsignedInt** attribute (only when **Message** is the parent element.) Contains the numeric return code of the error.|  
|Severity|Optional **String** attribute (only when **Message** is the parent element.) Contains the severity of the error.|  
|Description|Optional **String** attribute (only when **Message** is the parent element.) Contains the descriptive text of the error.|  
|Source|Optional **String** attribute (only when **Message** is the parent element.) Contains the name of the component that generated the error.|  
|HelpFile|Optional **String** attribute (only when **Message** is the parent element.) Contains the path or URL to the Help file or topic that describes the error.|  
  
## Remarks  
  