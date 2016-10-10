---
title: "Compiler Warning (level 1) CS0626"
ms.custom: na
ms.date: 10/02/2016
ms.devlang: 
  - CSharp
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2cd5061c-80e7-48d3-8d14-be7fc642af94
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
# Compiler Warning (level 1) CS0626
Method, operator, or accessor 'method' is marked external and has no attributes on it. Consider adding a DllImport attribute to specify the external implementation  
  
 A method marked `extern` should also be marked with an attribute, for example, the [DllImport](frlrfSystemRuntimeInteropServicesDllImportAttributeClassTopic) attribute.  
  
 The attribute specifies where the method is implemented. At run time, the program will need this information.  
  
 The following sample generates CS0626:  
  
```  
// CS0626.cs  
// compile with: /warnaserror  
using System.Runtime.InteropServices;  
  
public class MyClass  
{  
   static extern public void M(); // CS0626  
   // try the following line  
   // [DllImport("mydll.dll")] static extern public void M();  
  
   public static void Main()  
   {  
   }  
}  
```