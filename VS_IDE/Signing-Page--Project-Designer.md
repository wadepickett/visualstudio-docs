---
title: "Signing Page, Project Designer"
ms.custom: na
ms.date: 10/03/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-general
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: dab3ba13-2f92-4827-92bd-1be3c35bc48b
caps.latest.revision: 34
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
# Signing Page, Project Designer
Use the **Signing** page of the **Project Designer** to sign the application and deployment manifests and also to sign the assembly (strong-name signing).  
  
 Notice that the signing of application and deployment manifests is a process distinct from the signing of an assembly, although both tasks are performed on the **Signing** page.  
  
 Also, the storage of key-file information differs for manifest signing and assembly signing. For manifest signing, key information is stored in your computer's cryptographic storage database and the current user's Windows certificate store. For assembly signing, key information is stored only in your computer's cryptographic storage database.  
  
 To access the **Signing** page, select a project node in **Solution Explorer**, and then, on the **Project** menu, click **Properties**. When the **Project Designer** appears, click the **Signing** tab.  
  
## Application and Deployment Manifest Signing  
 **Sign the ClickOnce manifests** check box  
 Select this check box to sign the application and deployment manifests with a public/private key pair. For more information about how to do this, see [How to: Sign Application and Deployment Manifests](../VS_IDE/How-to--Sign-Application-and-Deployment-Manifests.md).  
  
 **Select from Store** button  
 Allows you to select an existing certificate from the current user's personal certificate store. You can select one of these certificates to sign your application and deployment manifests.  
  
 Clicking **Select from Store** opens the **Select a Certificate** dialog box, which lists certificates in your personal certificate store that are currently valid (not expired) and that have private keys. The purpose of the certificate you select should include code signing.  
  
 If you click **view certificate properties**, the **Certificate Details** dialog box appears. This dialog box includes detailed information about the certificate, and includes additional options. You can click **Learn more about certificates** to view additional Help information.  
  
 **Select from File** button  
 Allows you to select a certificate from an existing key file.  
  
 Clicking **Select from File** opens the **Select File** dialog box, which enables you to select a certificate key (.pfx) file. The file must be password protected and cannot already be located in your personal certificate store.  
  
 In the **Enter password to open file** dialog box, enter a password to open the certificate key (.pfx) file. The password information is stored in your personal key container list and your personal certificate store.  
  
 **Create Test Certificate** button  
 Allows you to create a certificate for testing. The test certificate is used for signing your ClickOnce application and deployment manifests.  
  
 Clicking **Create Test Certificate** opens the **Create Test Certificate** dialog box, in which you can type a password for the strong-name key file for the test certificate. The file is named *projectname*_TemporaryKey.pfx. If you click **OK** without typing a password, the .pfx file is not password encrypted.  
  
 **Timestamp server URL** box  
 Specifies the address of a server that timestamps your signature. When you provide a certificate, this external site verifies the time that the application was signed.  
  
## Assembly Signing  
 **Sign the assembly** check box  
 Select this check box to sign the assembly and create a strongly named key file. For more information about signing the assembly by using the **Project Designer**, see [How to: Sign an Assembly (Visual Studio)](assetId:///f468a7d3-234c-4353-924d-8e0ae5896564).  
  
 This option uses the Al.exe tool provided by the Windows Software Development Kit (SDK) to sign the assembly. For more information about Al.exe, see [How to: Sign an Assembly with a Strong Name](../Topic/How%20to:%20Sign%20an%20Assembly%20with%20a%20Strong%20Name.md).  
  
 **Choose a strong name key file** list  
 Enables you to specify a new or existing strongly named key file that is used to sign the assembly. Select **<Browse...>** to select an existing key file.  
  
 Select **<New...>** to create a new key file with which to sign the assembly. The **Create Strong Name Key** dialog box appears, which you can use to specify a key file name and protect the key file with a password. The password must be at least 6 characters long. If you specify a password, a Personal Information Exchange (.pfx) file is created; if you do not specify a password, a strongly named key (.snk) file is created.  
  
 **Change Password** button  
 Changes the password for the Personal Information Exchange (.pfx) key file that is used to sign the assembly.  
  
 Clicking **Change Password** opens the **Change Key Password** dialog box. In this dialog box, **Old password** is the current password for the key file. **New password** must be a least 6 characters long. The password information is stored in current user's Windows certificate store.  
  
 **Delay sign only** check box  
 Select this check box to enable delay signing.  
  
 Note that a delay signed project will not run and cannot be debugged. You can, however, use the [Sn.exe (Strong Name Tool)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) with the `-Vr` option to skip verification during development.  
  
> [!NOTE]
>  When you sign an assembly, you might not always have access to a private key. For example, an organization might have a closely guarded key pair that developers don’t have access to on a daily basis. The public key might be available, but access to the private key is restricted to a few individuals. In such a case, you can use *delayed* or *partial signing* to provide the public key, deferring the addition of the private key until the assembly is handed off.  
  
## See Also  
 [Project Properties Reference](../VS_IDE/Project-Properties-Reference.md)   
 [Managing Assembly and Manifest Signing](../VS_IDE/Managing-Assembly-and-Manifest-Signing.md)   
 [Strong-Name Signing for Managed Applications](assetId:///5fef3490-c519-4363-94fd-8b1ad260dab5)   
 [How to: Sign Application and Deployment Manifests](../VS_IDE/How-to--Sign-Application-and-Deployment-Manifests.md)   
 [How to: Sign an Assembly (Visual Studio)](assetId:///f468a7d3-234c-4353-924d-8e0ae5896564)   
 [How to: Sign an Assembly with a Strong Name](../Topic/How%20to:%20Sign%20an%20Assembly%20with%20a%20Strong%20Name.md)   
 [Strong-Named Assemblies](../Topic/Strong-Named%20Assemblies.md)