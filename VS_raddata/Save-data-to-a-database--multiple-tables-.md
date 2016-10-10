---
title: "Save data to a database (multiple tables)"
ms.custom: na
ms.date: 10/07/2016
ms.devlang: 
  - VB
  - CSharp
  - C++
  - aspx
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 7ebe03da-ce8c-4cbc-bac0-a2fde4ae4d07
caps.latest.revision: 24
manager: ghogen
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
# Save data to a database (multiple tables)
One of the most common scenarios in application development is to display data on a form in a Windows application, edit the data, and send the updated data back to the database. This walkthrough creates a form that displays data from two related tables and shows how to edit records and save changes back to the database. This example uses the `Customers` and `Orders` tables from the Northwind sample database.  
  
 You can save data in your application back to the database by calling the `Update` method of a TableAdapter. When you drag tables from the **Data Sources** window onto a form, the code that's required to save data is automatically added.Any additional tables that are added to a form require the manual addition of this code. This walkthrough shows how to add code to save updates from more than one table.  
  
> [!NOTE]
>  The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or the edition that you're using. To change your settings, choose **Import and Export Settings** on the **Tools** menu. For more information, see [Customizing Development Settings in Visual Studio](assetId:///22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Tasks illustrated in this walkthrough include:  
  
-   Creating a new **Windows Application** project.  
  
-   Creating and configuring a data source in your application with the [Data Source Configuration Wizard](../VS_raddata/media/Data-Source-Configuration-Wizard.png).  
  
-   Setting the controls of the items in the [Data Sources Window](../Topic/Data%20Sources%20Window.md). For more information, see [Set the control to be created when dragging from the Data Sources window](../VS_raddata/Set-the-control-to-be-created-when-dragging-from-the-Data-Sources-window.md).  
  
-   Creating data-bound controls by dragging items from the **Data Sources** window onto your form.  
  
-   Modifying a few records in each table in the dataset.  
  
-   Modifying the code to send the updated data in the dataset back to the database.  
  
## Prerequisites  
 In order to complete this walkthrough, you will need:  
  
-   Access to the Northwind sample database.  For more information, see [How to: Install Sample Databases](../VS_raddata/How-to--Install-Sample-Databases.md).  
  
## Create the Windows application  
 The first step is to create a **Windows Application**. Assigning a name to the project is optional during this step, but we'll give it a name because we're planning on saving it later.  
  
#### To create the new Windows application project  
  
1.  On the **File** menu, create a new project.  
  
2.  Name the project `UpdateMultipleTablesWalkthrough`.  
  
3.  Select **Windows Application**, and then select**OK**. For more information, see [Client Applications](../Topic/Developing%20Client%20Applications%20with%20the%20.NET%20Framework.md).  
  
     The **UpdateMultipleTablesWalkthrough** project is created and added to **Solution Explorer**.  
  
## Create the data source  
 This step creates a data source from the Northwind database using the **Data Source Configuration Wizard**. You must have access to the Northwind sample database to create the connection. For information about setting up the Northwind sample database, see [How to: Install Sample Databases](../VS_raddata/How-to--Install-Sample-Databases.md).  
  
#### To create the data source  
  
1.  On the **Data** menu, select**Show Data Sources**.  
  
2.  In the **Data Sources** window, select**Add New Data Source** to start the **Data Source Configuration Wizard**.  
  
3.  On the **Choose a Data Source Type**screen, select **Database**, and then select**Next**.  
  
4.  On the **Choose your Data Connection**screen do one of the following:  
  
    -   If a data connection to the Northwind sample database is available in the drop-down list, select it.  
  
         -or-  
  
    -   Select **New Connection** to open the **Add/Modify Connection** dialog box.  
  
5.  If your database requires a password, select the option to include sensitive data, and then select**Next**.  
  
6.  On the **Save connection string to the Application Configuration file**, select**Next**.  
  
7.  On the **Choose your Database Objects**screen, expand the **Tables** node .  
  
8.  Select the **Customers** and **Orders** tables, and then select **Finish**.  
  
     The **NorthwindDataSet** is added to your project, and the tables appear in the **Data Sources** window.  
  
## Set the controls to be created  
 For this walkthrough, the data in the `Customers` table is in a **Details** layout where data is displayed in individual controls. The data from the `Orders` table is in a **Grid** layout that's displayed in a <xref:System.Windows.Forms.DataGridView?qualifyHint=False> control.  
  
#### To set the drop type for the items in the Data Sources window  
  
1.  In the **Data Sources** window, expand the **Customers** node.  
  
2.  On the **Customers** node, select **Details** from the control list to change the control of the **Customers** table to individual controls. For more information, see [Set the control to be created when dragging from the Data Sources window](../VS_raddata/Set-the-control-to-be-created-when-dragging-from-the-Data-Sources-window.md).  
  
## Create the data-bound form  
 You can create the data-bound controls by dragging items from the **Data Sources** window onto your form.  
  
#### To create data-bound controls on the form  
  
1.  Drag the main **Customers** node from the **Data Sources** window onto **Form1**.  
  
     Data-bound controls with descriptive labels appear on the form, along with a tool strip (<xref:System.Windows.Forms.BindingNavigator?qualifyHint=False>) for navigating records. A [NorthwindDataSet](../VS_raddata/Dataset-tools-in-Visual-Studio.md), [CustomersTableAdapter](../VS_raddata/TableAdapter-Overview.md), <xref:System.Windows.Forms.BindingSource?qualifyHint=False>, and <xref:System.Windows.Forms.BindingNavigator?qualifyHint=False> appear in the component tray.  
  
2.  Drag the related **Orders** node from the **Data Sources** window onto **Form1**.  
  
    > [!NOTE]
    >  The related **Orders** node is located below the **Fax** column and is a child node of the **Customers** node.  
  
     A <xref:System.Windows.Forms.DataGridView?qualifyHint=False> control and a tool strip (<xref:System.Windows.Forms.BindingNavigator?qualifyHint=False>) for navigating records appear on the form. An [OrdersTableAdapter](../VS_raddata/TableAdapter-Overview.md) and <xref:System.Windows.Forms.BindingSource?qualifyHint=False> appear in the component tray.  
  
## Addcode to update the database  
 You can update the database by calling the `Update` methods of the **Customers** and **Orders** TableAdapters. By default, an event handler for the**Save** button of the<xref:System.Windows.Forms.BindingNavigator?qualifyHint=False> is added to the form's code to send updates to the database. This procedure modifies the code to send updates in the correct order.This eliminates the possibility of raising referential integrity errors. The code also implements error handling by wrapping the update call in a try-catch block. You can modify the code to suit the needs of your application.  
  
> [!NOTE]
>  For clarity, this walkthrough does not use a transaction.However, if you're updating two or more related tables, include all the update logic within a transaction. A transaction is a process that assures that all related changes to a database are successful before any changes are committed. For more information, see [Transactions and Concurrency](../Topic/Transactions%20and%20Concurrency.md).  
  
#### To add update logic to the application  
  
1.  Select the **Save** button on the <xref:System.Windows.Forms.BindingNavigator?qualifyHint=False>.This opens the Code Editor to the `bindingNavigatorSaveItem_Click` event handler.  
  
2.  Replace the code in the event handler to call the `Update` methods of the related TableAdapters. The following code first creates three temporary data tables to hold the updated information for each <xref:System.Data.DataRowState?qualifyHint=False> (<xref:System.Data.DataRowState?qualifyHint=False>, <xref:System.Data.DataRowState?qualifyHint=False>, and <xref:System.Data.DataRowState?qualifyHint=False>). Then updates are run in the correct order. The code should look like the following:  
  
     [!CODE [VbRaddataSaving#10](../CodeSnippet/VS_Snippets_VBCSharp/VbRaddataSaving#10)]  
  
## Test the application  
  
#### To test the application  
  
1.  Select**F5**.  
  
2.  Make some changes to the data of one or more records in each table.  
  
3.  Select the **Save** button.  
  
4.  Check the values in the database to verify that the changes were saved.  
  
## Next Steps  
 Depending on your application requirements, there are several steps you might want to perform after creating a data-bound form in your Windows application. Some enhancements you could make to this walkthrough include:  
  
-   Adding search functionality to the form. For more information, see [How to: Add a Parameterized Query to a Windows Forms Application](../Topic/How%20to:%20Add%20a%20Parameterized%20Query%20to%20a%20Windows%20Forms%20Application.md).  
  
-   Editing the data source to add or remove database objects. For more information, see [How to: Edit a Dataset](../Topic/How%20to:%20Edit%20a%20Dataset.md).  
  
## See Also  
 [Save data back to the database](../VS_raddata/Save-data-back-to-the-database.md)