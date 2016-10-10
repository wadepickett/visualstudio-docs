---
title: "How to: Set Debug and Release Configurations"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - FSharp
  - VB
  - CSharp
  - C++
  - JScript
  - VB
  - CSharp
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-debug
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 57b6bbb7-f2af-48f7-8773-127d75034ed2
caps.latest.revision: 45
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# How to: Set Debug and Release Configurations
Visual Studio projects have separate release and debug configurations for your program. As the names imply, you build the debug version for debugging and the release version for the final release distribution.  
  
 The debug configuration of your program is compiled with full symbolic debug information and no optimization. Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.  
  
 The release configuration of your program contains no symbolic debug information and is fully optimized. Debug information can be generated in PDB Files, depending on the compiler options that are used. Creating PDB files can be very useful if you later have to debug your release version.  
  
 For more information about build configurations, see [Understanding Build Configurations](../VS_IDE/Understanding-Build-Configurations.md).  
  
 You can change the build configuration from the **Build** menu, from the toolbar, or in the project’s property pages. Project property pages are language-specific. The procedure below shows how to change the build configuration from the menu and the toolbar. For more information about how to change the build configuration in projects in different languages, see the Related Topics section below.  
  
### To change the build configuration  
  
1.  From the Build menu: click **Build / Configuration Manager**, then select **Debug** or **Release**.  
  
2.  On the toolbar, choose either **Debug** or **Release** from the **Solution Configurations** list box.  
  
     ![toolbar build configuration](../VS_debugger/media/ToolbarBuildConfiguration.png "ToolbarBuildConfiguration")  
  
     This toolbar is not available in Express editions. You can use the **Build Solution F6** and **Start Debugging F5** menu items to choose the configuration.  
  
## See Also  
 [Debugger Settings and Preparation](../VS_debugger/Debugger-Settings-and-Preparation.md)   
 [Project Settings for a C++ Debug Configuration](../VS_debugger/Project-Settings-for-a-C---Debug-Configuration.md)   
 [Project Settings for  C# Debug Configurations](../VS_debugger/Project-Settings-for--C#-Debug-Configurations.md)   
 [Project Settings for a Visual Basic Debug Configuration](../VS_debugger/Project-Settings-for-a-Visual-Basic-Debug-Configuration.md)   
 [How to: Create and Edit Configurations](../VS_IDE/How-to--Create-and-Edit-Configurations.md)   
 [Debug and Release Project Configurations](assetId:///0440b300-0614-4511-901a-105b771b236e)