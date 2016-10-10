---
title: "&#39;System.ObsoleteAttribute&#39; cannot be applied to the &#39;AddHandler&#39;, &#39;RemoveHandler&#39;, or &#39;RaiseEvent&#39; definitions"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2bddde2e-9ca0-4f72-8910-0789a6350af8
caps.latest.revision: 5
manager: douge
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# &#39;System.ObsoleteAttribute&#39; cannot be applied to the &#39;AddHandler&#39;, &#39;RemoveHandler&#39;, or &#39;RaiseEvent&#39; definitions
'System.ObsoleteAttribute' cannot be applied to the 'AddHandler', 'RemoveHandler', or 'RaiseEvent' definitions. If required, apply the attribute directly to the event.  
  
 A custom event applies the <xref:System.ObsoleteAttribute?qualifyHint=False> to its `AddHandler`, `RemoveHandler`, or `RaiseEvent` procedure.  
  
 The <xref:System.ObsoleteAttribute?qualifyHint=False> marks a programming element as no longer in use and informs users that the element is to be removed in future versions of the product.  
  
 It is not meaningful to have certain parts of a custom event still in use while others are no longer in use.  
  
 **Error ID:** BC31142  
  
### To correct this error  
  
-   Remove the <xref:System.ObsoleteAttribute?qualifyHint=False> from the individual procedure declaration and apply it to the overall event declaration.  
  
## See Also  
 <xref:System.ObsoleteAttribute?qualifyHint=False>   
 [Event Statement](../Topic/Event%20Statement.md)   
 [AddHandler Statement](../Topic/AddHandler%20Statement.md)   
 [RemoveHandler Statement](../Topic/RemoveHandler%20Statement.md)   
 [RaiseEvent Statement](../Topic/RaiseEvent%20Statement.md)