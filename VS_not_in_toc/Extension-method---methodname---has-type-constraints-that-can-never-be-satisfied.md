---
title: "Extension method &#39;&lt;methodname&gt;&#39; has type constraints that can never be satisfied"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ff42d6e9-611b-407d-a269-f268b36ed277
caps.latest.revision: 11
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
# Extension method &#39;&lt;methodname&gt;&#39; has type constraints that can never be satisfied
The type parameters of this method interact in a way that prevents them from ever being satisfied. The following extension method is an example.  
  
```  
'' Not valid.  
'<Extension()> _  
'Sub extensionExample(Of T As U, U)(ByVal para1 As T, ByVal para2 As U)  
'End Sub  
```  
  
 Because the method is an extension method, the compiler must be able to determine the data type or types that the method extends based only on the first parameter in the method declaration, `para1`, and the argument sent in for that parameter. When the first parameter refers to generic type parameters, `para1 as T`, the constraints on the generic parameters restrict the set of types to which the method applies.  
  
 Applicability of an extension method is determined from the argument provided for the first parameter, which is `arg1` in the following code.  
  
 `'' Not valid.`  
  
 `'arg1.extensionExample(arg2)`  
  
 It must be possible to verify the constraints on all generic type parameters referred to by the first parameter, `para1`, by looking at only the first argument, `arg1`. In `extensionExample`, the set of types that is being extended cannot be determined from the first parameter alone. Type parameter `T` is constrained by type parameter `U`, which is not referenced by `para1` and cannot be inferred from `arg1`. Therefore, the applicability of the method to any possible type cannot be verified, and the method can never be called.  
  
 **Error ID:** BC36561  
  
### To correct this error  
  
-   Change the type declaration to remove the interdependence between the types.  
  
## See Also  
 [Extension Methods](../Topic/Extension%20Methods%20\(Visual%20Basic\).md)   
 [Generic Types in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)