---
title: "Using a Custom Registration Attribute to Register an Extension"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 98068fa7-bda1-4922-b3f6-28680de58c3d
caps.latest.revision: 3
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
# Using a Custom Registration Attribute to Register an Extension
In certain cases you may need to create a new registration attribute for your extension. You can use registration attributes to add new registry keys or to add new values to existing keys. The new attribute must derive from <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute?qualifyHint=False>, and it must override the <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register?qualifyHint=False> and <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister?qualifyHint=False> methods.  
  
## Creating a Custom Attribute  
 The following code shows how to create a new registration attribute.  
  
```  
[AttributeUsage(AttributeTargets.Class, Inherited = true, AllowMultiple = false)]  
    public class CustomRegistrationAttribute : RegistrationAttribute  
    {  
    }  
  
```  
  
 The <xref:System.AttributeUsageAttribute?qualifyHint=False> is used on attribute classes to specify the program element (class, method, etc.) to which the attribute pertains, whether it can be used more than once, and whether it can be inherited.  
  
### Creating a Registry Key  
 In the following code, the custom attribute creates a **Custom** subkey under the key for the VSPackage that is being registered.  
  
```  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + @"}\Custom");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
    }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveKey(@"Packages\" + context.ComponentType.GUID + @"}\Custom");  
}  
  
```  
  
### Creating a New Value Under an Existing Registry Key  
 You can add custom values to an existing key. The following code shows how to add a new value to a VSPackage registration key.  
  
```  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + "}");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
                }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveValue(@"Packages\" + context.ComponentType.GUID, "NewCustom");  
}  
  
```