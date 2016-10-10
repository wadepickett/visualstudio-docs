---
title: "Working with 3-D Assets for Games and Apps"
ms.custom: na
ms.date: 10/03/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-general
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 910d673b-c884-4eeb-9928-0e89f3d38cb6
caps.latest.revision: 24
manager: ghogen
---
# Working with 3-D Assets for Games and Apps
This document describes the Visual Studio tools that you can use to create or modify 3-D models, textures, and shaders for DirectX-based games and apps.  
  
## DirectX app development in Visual Studio  
 A DirectX app typically combines programming logic, the DirectX API, and High Level Shading Language (HLSL) programs, together with audio and 3-D visual assets to present a rich, interactive multimedia experience.Visual Studio includes tools that you can use to work with images and textures, 3-D models, and shaders without leaving the IDE to use another tool. The Visual Studio tools are especially suited for creating *placeholder* assets, which you can use to test code or build prototypes before you commission production-ready assets, and for inspecting and modifying production-ready assets when you are debugging your app.  
  
 Here's more information about the kinds of assets that you can work with in Visual Studio.  
  
### Images and textures  
 Images and textures provide color and visual detail in games and apps. In 3-D graphics, textures come in a variety of formats, types, and geometries to support different uses. For example, normal maps provide per-pixel surface normals for more-detailed lighting of 3-D models, and cube maps provide texture in all directions for uses such as sky-boxing, reflections, and spherical texture mapping. Textures can provide mip maps to support efficient rendering at different levels of detail, and can support different color channels and color orderings. Textures can be stored in a variety of compressed formats that occupy less dedicated graphics memory and help GPUs access textures more efficiently.  
  
 You can use the Visual Studio Image Editor to work with images and textures in many common types and formats.  
  
### 3-D models  
 3-D models create space and shape in games and apps. Minimally, models encode the position of points in 3-D space—which are known as *vertices*—together with indexing data to define lines or triangles that represent the shape of the model. Additional data can be associated with these vertices—for example, color information, normal vectors, or application-specific attributes. Each model can also define object-wide attributes—for example, which shader is used to compute the appearance of the object's surface, or which texture is applied to it.  
  
 You can use the Visual Studio Model Editor to work with 3-D models in several common formats.  
  
### Shaders  
 Shaders are small, domain-specific programs that run on the graphics processing unit (GPU). Shaders determine how 3-D models are transformed into on-screen shapes and how each pixel in those shapes is colored. By creating a shader and applying it to an object in your game or app, you can give the object a unique appearance.  
  
 You can use the Visual Studio Shader Designer, which is a graph-based shader design tool, to create custom visual effects without knowing HLSL programming.  
  
> [!NOTE]
>  For more information about how to start with DirectX programming, see [DirectX](http://go.microsoft.com/fwlink/p/?LinkId=224633). For more information about how to debug a DirectX-based app, see [Graphics Diagnostics (Debugging DirectX Graphics)](../VS_debugger/Visual-Studio-Graphics-Diagnostics.md).  
  
## DirectX version compatibility  
 Visual Studio uses DirectX to render 2-D and 3-D assets. You can select either the DirectX 11 renderer, or the Windows Advanced Rasterization Platform (WARP) software renderer. The DirectX 11 renderer provides high-performance, hardware-accelerated rendering on DirectX 11 and DirectX 10 GPUs. The WARP renderer helps make sure that your assets work with a broad range of computers—this includes computers that don't have modern graphics hardware and computers that have integrated graphics hardware. For more information about WARP, see [Windows Advanced Rasterization Platform (WARP) Guide](http://go.microsoft.com/fwlink/p/?LinkId=224634).  
  
## Related topics  
  
|Title|Description|  
|-----------|-----------------|  
|[Working with Textures and Images](../VS_IDE/Working-with-Textures-and-Images.md)|Describes how to use Visual Studio to work with images and textures.|  
|[Working with 3-D Models](../VS_IDE/Working-with-3-D-Models.md)|Describes how to use Visual Studio to work with 3-D models.|  
|[Working with Shaders](../VS_IDE/Working-with-Shaders.md)|Describes how to use the Visual Studio Shader Designer to create and modify custom shader effects.|  
|[Using 3-D Assets in Your Game or App](../VS_IDE/Using-3-D-Assets-in-Your-Game-or-App.md)|Describes how to use assets, which you created by using the Image Editor, Model Editor, or Shader Designer, in your game or app.|