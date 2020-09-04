---
title: "Supported MDX (Analysis Services MDX) | Microsoft Docs"
description: Learn about the statements and functions that are supported within Multidimensional Expressions (MDX) script.
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
---
# Supported MDX (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  The following statements and functions are supported within Multidimensional Expressions (MDX) Script:  
  
 [&#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx-double-slash)  
  
 [-- &#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx-operator-reference)  
  
 [Comment &#40;MDX&#41;](/sql/mdx/comment-mdx)  
  
 [ALTER CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-alter-cube)  
  
> [!NOTE]  
>  Only altering the default member is supported in MDX Scripting.  
  
 [CALCULATE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate)  
  
 [CASE Statement &#40;MDX&#41;](/sql/mdx/case-statement-mdx)  
  
 [CREATE CELL CALCULATION Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-cell-calculation)  
  
 [CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member)  
  
 [CREATE SET Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-set)  
  
 [EXISTING Keyword &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-query-existing-keyword.md)  
  
 [FREEZE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-freeze)  
  
 [IF Statement  &#40;MDX&#41;](/sql/mdx/mdx-scripting-if)  
  
 [This &#40;MDX&#41;](/sql/mdx/this-mdx)  
  
> [!NOTE]  
>  MDX supports assignment to the following cell properties: **BACK_COLOR**, **FORE_COLOR**, **FORMAT_STRING**, **FONT_FLAGS**, **FONT_NAME**, and **FONT_SIZE**. For more information, see [Using Cell Properties &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-cell-properties-using-cell-properties.md). MDX also supports assignment to the **NON_EMPTY_BEHAVIOR** property of the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.  
  
 [SCOPE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope)  
  
## See Also  
 [The Basic MDX Script &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/the-basic-mdx-script-mdx.md)  
  
  
