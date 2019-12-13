---
title: "Install Business Central Using Setup"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
ms.assetid: e4bd0a48-9e21-44e3-8a5d-858f02af5206
caps.latest.revision: 24
ms.author: jswymer
author: jswymer
---

# Installing Business Central Using Setup

You use [!INCLUDE[prodsetup](../developer/includes/prodsetup.md)] to install the different components that comprise a [!INCLUDE[prodshort](../developer/includes/prodshort.md)] production, demonstration, or development environment. For a list of components, see [Components and Topology](product-and-architecture-overview.md).

## About Setup

Setup is available on the installation media (DVD) in the setup.exe file. When run, Setup leads you through installation process, where you can install individual components or select predefined options that install a logical collection of components.

### Configuration settings

Throughout Setup, you are presented with various configuration settings. Some settings require that you set them, and other settings have a default value. In many cases, the default value is sufficient for the initial installation. After you run Setup, you can change the configuration settings by using other tools such as the [!INCLUDE[admintool](../developer/includes/admintool.md)] and [!INCLUDE[adminshell](../developer/includes/adminshell.md)].

### Prerequisite Installations by Setup

There are some components that require other software in order run, for example the database requires SQL Server and the Web client requires IIS. Setup will install several of these prerequisites, like installing SQL Server Express and enabling IIS. You can see which prerequisites Setup installs in the [System Requirements](system-requirement-business-central.md).  

## Before you run Setup

1. Plan your deployment and identify the components that you want to install.
2. Verify that the target computer where you will install components meets the hardware and software requirements for the components that you want to install. For more information, see [System Requirements](system-requirement-business-central.md).
3. Make sure that you are an administrator on the computer where you run Setup.
4. Determine the HTTP ports that you will use for components.

    During setup, you will have to specify the following HTTP ports:

    |Port | Description|Default|
    |--------|------------|-------|
    | Management services| The listening TCP port for the Business Central Server Administration tool.|7045|
    | Client services| The listening HTTP port for client services.|7046|
    | SOAP services| The listening HTTP port for SOAP web services.|7047|
    | OData service|The listening HTTP port for OData web services.|7048|
    | Developer services|The listening HTTP port for Microsoft Dynamics NAV Developer web services|7049|

    You must either select a port number that is not being used by another service, or stop/disable the other service before you run setup. For example, if you have an older version of [!INCLUDE[nav_server_md.md](../developer/includes/nav_server_md.md)] or [!INCLUDE[server](../developer/includes/server.md)] installed, then configure the new server instance to use other ports than the old server instance, or stop the old server instance before you install the new one.

## Run Setup

<!--
 or to capture a set of custom setup settings to save in a setup configuration file. In this procedure, you run [!INCLUDE[prodsetup](../developer/includes/prodsetup.md)] without any customization or configuration. Opportunities for customization and configuration are described throughout the procedure.
-->  
1. In the installation media (DVD) folder, double-click the setup.exe.
2. Follow Setup until you get to the **[!INCLUDE[prodlong](../developer/includes/prodlong.md)]** page.

    ![Business Central Setup](../media/setup.png "Business Central Setup")

    - Choose **Get a free online trial to sign-up**  if you interested in hearing about and trying the cloud experience.
    - Choose **Get the Business Central app from the Microsoft Store** to download a companion app that mimics that Web client but has the same look-and-feel as the mobile apps. For more information, see [Installing Installing the Microsoft Dynamics 365 Business Central App](install-business-central-app.md).
    - Choose **Advance installation options** to install a demonstration environment or one more components. Then, follow the on-screen instructions to complete the installation.

## Cancel Setup

Setup does not provide a **Cancel** button on all pages, but you can cancel an installation from any page by choosing the **Close** button in the upper-right corner. All [!INCLUDE[prodshort](../developer/includes/prodshort.md)] components are removed from the computer. The only software that Setup cannot remove are:  

- Database files, such as the Demo database.  

- Prerequisites for [!INCLUDE[prodshort](../developer/includes/prodshort.md)] components that Setup can install, such as the .NET Framework. 

## Run Setup from a command prompt

You can run [!INCLUDE[prodsetup](../developer/includes/prodsetup.md)] from a command prompt, either by pointing to its location on the installation media, or after the initial installation, from the location where the Setup.exe is automatically stored on your computer. The default location is:  
  
```  
C:\Program Files (x86)\Common Files\Microsoft Dynamics 365 Business Central\<Version number>\Setup  
```  

You can use the following options with Setup.exe.  
  
|Setup option|Description|  
|------------------|-----------------|  
|**/config \<Setup config file>**|Specifies path and file name information for a Setup configuration file to load.<br /><br /> This is the only required option.|  
|**/help**|Displays Help about Setup.exe options.|  
|**/log \<log path>**|Specifies path and file name information for a Setup log file to be created by Setup. The file must not exist before you run Setup.|  
|**/quiet**|Specifies that Setup does not display anything on the screen. All configuration information is taken from the specified configuration file.|  
|**/repair**|Repairs the current installation of [!INCLUDE[prodshort](../developer/includes/prodshort.md)].|  
|**/uninstall**|Removes the current installation [!INCLUDE[prodshort](../developer/includes/prodshort.md)].|

## Save, Edit, and Load a Setup Configuration File
During Setup, you can save the configuration settings to a file before you finish and exit Setup. Then later, you can load use Setup to load the configuration file to make it faster to replicate the same configuration for another deployment.
  
#### Save to a Setup configuration file

1. Choose **Save** on the **Specify parameters** page in Setup. This page is available when you run Setup unless you select **Install Demo**, which skips all other Setup pages.  
  
2. Type a file name for the configuration file. An .xml extension is added automatically.  
  
3. Choose **Save**.  
  
     You now return to the **Specify parameters** page, where you can continue with installing software. You can also close Setup if you only have to create a Setup configuration file. 

#### Edit a Setup configuration file

You edit the file using an XML editor or text editor. Setup configuration files contain two types of settings.  
  
|Setting type|Purpose|  
|------------------|-------------|  
|Component|For each component, there are three separate values, all displayed on a single line:<br /><br /> -   **ShowOptionNode**<br />     Specifies whether the component should be displayed in Setup. For silent installs, this parameter is not relevant.<br />-   **State**<br />     There are two possible values: **Local**, indicates that the component is included in the install, and **Absent** indicates that the component is not included.<br />-   **Id**<br />     Identifies the component<br /><br /> You can change value for **State** or **ShowOptionNode**, but not for **Id**. Also, you cannot add or remove a component.|  
|Parameter|These settings contain configuration information for components. As with Components, you can modify a parameter’s **Value**, but not its **Id**. |  

  
#### Load a Setup configuration file
  
The option to load a Setup configuration file is on the **Choose an installation option** page in Setup.

> [!NOTE] 
> If you are using a Setup configuration file that was created from an earlier version of [!INCLUDE[prodshort](../developer/includes/prodshort.md)] or [!INCLUDE[navnow_md.md](../developer/includes/navnow_md.md)], be aware that there might be some elements that are no longer supported because the feature has been deprecated. For example, the elements that have the following IDs are no longer supported as og 2019 release wave 2: "RoleTailoredClient", "ExcelAddin, "ClassicClient", "ClickOnceInstallerTools", "STOutlookIntegration", "PublicWinBaseUrl", and "ACSUri".


1. On the **Choose an installation option** page, choose **Load Configuration**.  
  
    This option is located under **Custom Components**. 

    > [!IMPORTANT]  
    > A Setup configuration file contains information about which components to install and which settings to apply to each component. Therefore, you should not customize the list of components or configure components in Setup before you load a Setup configuration file because loading the configuration overwrites all prior customization and configuration.
  
2. In the **Open** dialog box, select or browse to the Setup configuration file that you want to open, and then double-click the file.  
  
     Setup now shows the **Customize the installation** page that has been modified according to the component selection in the loaded Setup configuration file.  
  
3. Modify the list of components to install or choose **Next** to proceed to the **Specify parameters** page, where settings from the Setup configuration file are shown.  
  
4. Configure these settings or choose **Apply** to accept these values and continue.

## See Also

 [Components](product-and-architecture-overview.md)  
 [Deployment](deployment.md)  
