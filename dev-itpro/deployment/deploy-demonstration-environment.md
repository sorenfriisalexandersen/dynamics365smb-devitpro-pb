---
title: "Deploying Business Central a Demonstration Environment"
ms.custom: na
ms.date: 11/06/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: jswymer
---
# Deploying the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] Demonstration Environment

This deployment scenario installs the major [!INCLUDE[prodshort](../developer/includes/prodshort.md)] components on a single computer, complete with a base application and database with demonstration data. After the installation, you will have an end-to-end environment, where you can access [!INCLUDE[prodshort](../developer/includes/prodshort.md)] data from the Web client. The installation requires minimal hardware resources, preparation, and configuration.  

## Installed Components and Configuration  

### Components  
 This scenario installs the following components:  

-   [!INCLUDE[webservercomponents](../developer/includes/webservercomponents.md)]  

-   Internet Information Services

    If IIS is already installed, then the setup will enable any required features that are not currently enabled.

-    [!INCLUDE[server](../developer/includes/server.md)]  

-   SQL Server Database Components, including [!INCLUDE[demolong](../developer/includes/demolong_md.md)] and demo license.

    For information about what you can do with this license, see [Properties of the Demo License](Demo-License.md).      

-    [!INCLUDE[admintool](../developer/includes/admintool.md)] 

-    Al Development Environment

### Configuration  
This scenario uses the default setting of [!INCLUDE[prodsetup](../developer/includes/prodsetup.md)], which includes the following:  

-   [!INCLUDE[webserver](../developer/includes/webservercomponents.md)]
 
    - Port: 8080 (inbound rule automatically added to Windows Firewall)
    - Protocol: HTTP

-   Windows authentication for authenticating users.  

-   [!INCLUDE[server](../developer/includes/server.md)] configuration:  

    -   Service instance: [!INCLUDE[serverinstance](../developer/includes/serverinstance.md)]  

    -   Client service port: 7046  

    -   SOAP web services port: 7047  

    -   OData web services port: 7048  

-   [!INCLUDE[prodshort](../developer/includes/prodshort.md)] database components configuration:  

    -   Service instance: BCDEMO  

    -   Database: Demo Database BC (15-0)  

-   NETWORK SERVICE account is used as the service account for [!INCLUDE[server](../developer/includes/server.md)] and database.  

## Prepare for the [!INCLUDE[nav_web](../developer/includes/nav_web_md.md)] installation  

1.  Get access to the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] installation media. For example, this could be a DVD or network drive that contains the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] installation files.  

2.  Make sure that the computer meets the hardware and software requirements.  

    For more information, see [System Requirements](system-requirement-business-central.md).  


## Run [!INCLUDE[prodsetup](../developer/includes/prodsetup.md)]  

1.  From the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] installation media, run the setup.exe file to start the [!INCLUDE[prodsetup](../developer/includes/prodsetup.md)].  

2. Follow the setup until you get to the **[!INCLUDE[prodlong](../developer/includes/prodlong.md)]** page, then choose **Advanced installation option** > **Install Demo**.  

    The installation starts. This can take several minutes.  

## Open the [!INCLUDE[nav_web](../developer/includes/nav_web_md.md)]  

-   To open the [!INCLUDE[nav_web](../developer/includes/nav_web_md.md)] from the computer where you installed [!INCLUDE[prodshort](../developer/includes/prodshort.md)], on the **Start** menu, choose **All Programs**, and then choose **[!INCLUDE[prodshort](../developer/includes/prodshort.md)] Web Client**.  

-   To open the [!INCLUDE[nav_web](../developer/includes/nav_web_md.md)] from other devices on the network, open an Internet browser, and type the following URL in the address box:

    ```
    https://ComputerName:8080/BC150  
    ```
    Substitute **ComputerName** with the name of the computer where you installed [!INCLUDE[prodshort](../developer/includes/prodshort.md)]. If you are working on the computer where you installed [!INCLUDE[prodshort](../developer/includes/prodshort.md)], then you can use **localhost**.  

    For example:

    ```
    https://localhost:8080/BC150 
    ```

## See Also  
[Business Central Web Server Overview](web-server-overview.md)   
 
