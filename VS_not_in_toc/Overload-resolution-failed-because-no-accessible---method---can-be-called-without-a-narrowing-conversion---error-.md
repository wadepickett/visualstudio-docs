---
title: "Overload resolution failed because no accessible &#39;&lt;method&gt;&#39; can be called without a narrowing conversion: &lt;error&gt;"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3b3e724d-6fad-4146-b47d-6525493b2fa8
caps.latest.revision: 8
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
# Overload resolution failed because no accessible &#39;&lt;method&gt;&#39; can be called without a narrowing conversion: &lt;error&gt;
You have made a call to an overloaded method, but the compiler cannot find a method that can be called without a narrowing conversion. A narrowing conversion changes a value to a data type that might not be able to precisely hold some of the possible values.  
  
 **Error ID:** BC30519  
  
### To correct this error  
  
-   Specify `Option Strict Off`.  
  
## See Also  
 [Overloaded Properties and Methods](../Topic/Overloaded%20Properties%20and%20Methods%20\(Visual%20Basic\).md)   
 [Widening and Narrowing Conversions](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)   
 [Option Strict Statement](../Topic/Option%20Strict%20Statement.md)