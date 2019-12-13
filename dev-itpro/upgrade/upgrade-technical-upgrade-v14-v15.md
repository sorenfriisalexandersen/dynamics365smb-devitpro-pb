---
title: Technical Upgrade 
description: The article explains how to upgrade the application code and how to merge code from different versions of the application.
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: jswymer
author: jswymer
ms.service: "dynamics365-business-central"
---
# Technical Upgrade to [!INCLUDE[prodlong](../developer/includes/prodlong.md)] 2019 Wave 2

<!--
> [!IMPORTANT]  
> [!INCLUDE[vnext_preview](../developer/includes/vnext_preview.md)] 
>
> Please note that this topic is a draft in progress. We are still working on adding more details to the steps described in this topic.
-->
Use this process when you have a code customized [!INCLUDE[prodshort](../developer/includes/prodshort.md)] application (version 14) that you want to upgrade to the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] 2019 release wave 2 platform (version 15). This will not upgrade the application to the latest version. With this process, you will convert the entire application from C/AL to an AL base application extension.

<!-- For this scenario, I used a BC 14.0 modified base application on a BC 14.0 server instance, which include some customization on C/AL objects in the base application and a custom extension that modified the Item table. is proecess will convert the entire BC 14 custom application to an Extension on the BC 15 platform.-->

 ![Upgrade on customized Business Central application](../developer/media/bc15-upgrade-customized-app.png "Upgrade on customize Business Central application")  
 

#### Single-tenant and multitenant deployments

The process for upgrading the very similar for a single-tenant and multitenant deployment. However, there are some inherent differences because with a single-tenant deployment, the application and business data are included in the same database, while with a multitenant deployment application code is in a separate database (the application database) than the business data (tenant). In the procedures that follow, for a single-tenant deployment, consider references to the *application database* and *tenant database* as the same database. Steps are marked as *Single-tenant only* or *Multitenant only* where applicable.

## Prerequisites

1. Upgrade to Business Central Spring 2019 [Cumulative Update 5](https://support.microsoft.com/help/4522949) (version 14.6).

   If your current deployment is already running cumulative update 6 (version 14.7), we recommend to wait until the Update 2 for version 15 is released.

For more information, see [Upgrading to Dynamics 365 Business Central On-Premises](upgrading-to-business-central-on-premises.md).

<!-- Replace step 1 with this for CU1
1. Upgrade to the latest Business Central Spring 2019 Cumulative Update (version 14.X) that is compatible with the version 15 .

   If your current deployment is already running cumulative update 5 (version 14.6), we recommend to wait until the first cumulative update for version 15 is released. This is recommended because of destructive schema changes introduced by version 15 Base Application.

 For more information, see [Upgrading to Dynamics 365 Business Central On-Premises](upgrading-to-business-central-on-premises.md).

-->
## Task 1: Install [!INCLUDE[prodlong](../developer/includes/prodlong.md)] 2019 release wave 2 (version 15.0)

1. Before you install version 15, it can be useful to create desktop shortcuts to the version 14.0 tools, such as the [!INCLUDE[admintool](../developer/includes/admintool.md)], [!INCLUDE[adminshell](../developer/includes/adminshell.md)], and [!INCLUDE[devshell](../developer/includes/devshell.md)] because the Start menu items for these will be replaced with the version 15.0 tools.

2. Install all components of Business Central 2019 release wave 2 (version 15).

    If you did not uninstall version 14.0, then you must either specify different port numbers for components (like the [!INCLUDE[server](../developer/includes/server.md)] instance and web services) during installation, or you must stop the version 14.0 [!INCLUDE[server](../developer/includes/server.md)] instance before you run the installation. Otherwise, you will get an error that the [!INCLUDE[server](../developer/includes/server.md)] failed to install.

    <!--
    > [!IMPORTANT]
    > Because of dependencies, we recommend that for upgrade , you install all components available. Also, there is currently a known issue with the Microsoft.Office.Interop.Word.dll. After installation, you must copy the Microsoft.Office.Interop.Word.dll from the C:\Program Files (x86)\Microsoft Dynamics 365 Business Central\150\RoleTailored Client folder to the C:\Program Files\Microsoft Dynamics 365 Business Central\150\Service\Add-ins folder.-->

    For more information, see [Installing Business Central Using Setup](../deployment/install-using-setup.md).

3. Copy the version 14 **CodeViewer** add-in to the version 15.0 server installation.

    Copy the **CodeViewer** folder from the **Add-ins** folder of the Business Central version 14 RoleTailored client installation (C:\Program Files (x86)\Microsoft Dynamics 365 Business Central\140\RoleTailored Client\Add-ins) to the **Add-ins** folder of the Business Central 150 Server installation (C:\Program Files\Microsoft Dynamics 365 Business Central\150\Service\Add-ins). Replace the existing folder and files, if any.
     
    In version 15.0 CodeViewer is no longer used, but it is required because of references that exist in the converted application. If you omit this step, you might get compilation errors later.

## Task 2: Convert your application from C/AL to AL

Convert your solution from C/AL code to AL code. For more information, see [Code Conversion from C/AL to AL](devenv-code-conversion.md).

## <a name="Preparedb"></a> Task 3: Prepare the application database for technical upgrade

1. Make backup of the database.
2. Make sure that you have access to the extension packages for all published extensions.

    You will need these later to publish and install the extensions again.
3. Uninstall all extensions from the old tenants.

    Run the [!INCLUDE[adminshell](../developer/includes/adminshell.md)] for version 14.0 as an administrator). To uninstall an extension, you use the [Uninstall-NAVApp](/powershell/module/microsoft.dynamics.nav.apps.management/uninstall-navapp) cmdlet. For example, together with the Get-NAVAppInfo cmdlet, you can uninstall all extensions with a single command:

    ``` 
    Get-NAVAppInfo -ServerInstance <BC14 server instance> -Tenant <tenant ID> | % { Uninstall-NAVApp -ServerInstance <BC14 server instance> -Name $_.Name -Version $_.Version -Tenant <tenant ID>}
    ``` 

    If you have a single tenant deployment, you can omit the `-Tenant` parameter and value. 

3. Unpublish all extensions from the application server instance.

    To unpublish extensions, use the [Unpublish-NAVAPP cmdlet](/powershell/module/microsoft.dynamics.nav.apps.management/unpublish-navapp). Together with the [Get-NAVAppInfo cmdlet](/powershell/module/microsoft.dynamics.nav.apps.management/get-navappinfo?view=businesscentral-ps), you can uninstall all extensions from the tenant using a single command:

    ```
    Get-NAVAppInfo -ServerInstance <BC14 server instance> | % { Unpublish-NAVApp -ServerInstance <BC14 server instance> -Name $_.Name -Version $_.Version }
    ```

4. Unpublish all system, test, and application symbols.

    To unpublish symbols, use the Unpublish-NAVAPP cmdlet with the `-SymbolsOnly` switch.

    ``` 
    Get-NAVAppInfo -ServerInstance <BC14 server instance> -SymbolsOnly | % { Unpublish-NAVApp -ServerInstance <BC14 server instance> -Name $_.Name -Version $_.Version }
    ```    

    [What are symbols?](upgrade-overview-v15.md#Symbols)  

5. (Multitenant only) Dismount the tenants from the application server instance.

    To dismount a tenant, use the [Dismount-NAVTenant](/powershell/module/microsoft.dynamics.nav.management/dismount-navtenant) cmdlet:

    ```
    Dismount-NAVTenant -ServerInstance <BC14 server instance> -Tenant <tenant ID>
    ```

6. Stop the server instance.

    ```
    Stop-NAVServerInstance -ServerInstance <BC14 server instance>
    ```

## Task 4: Convert the version 14.0 application database to the version 15.0 platform

This task runs a technical upgrade on the application database to convert it from the version 14.0 platform to the version 15.0 platform. The conversion updates the system tables of the database to the new schema (data structure) and provides the latest platform features and performance enhancements.

1. Start [!INCLUDE[adminshell](../developer/includes/adminshell.md)] for version 15.0 as an administrator.
2. Run the [Invoke-NAVApplicationDatabaseConversion cmdlet](/powershell/module/microsoft.dynamics.nav.management/invoke-navapplicationdatabaseconversion) to start the conversion:

    ```
    Invoke-NAVApplicationDatabaseConversion -DatabaseServer <database server>\<database instance> -DatabaseName "<BC14 database name>"
    ```
    When completed, a message like the following displays in the console:

    ```
    DatabaseServer      : .\BCDEMO
    DatabaseName        : Demo Database BC (14-0)
    DatabaseCredentials :
    DatabaseLocation    :
    Collation           :
    ```
## Task 5: Connect and configure the version 15 server instance

When you installed version 15 in **Task 1**, a version 15 [!INCLUDE[server](../developer/includes/server.md)] instance was created. In this task, you change server configuration settings that are required to complete the upgrade. Some of the changes are only required for version 14 to version 15.0 upgrade and can be reverted after you complete the upgrade.

1. Set the server instance to connect to the application database.

    ```
    Set-NAVServerConfiguration -ServerInstance <BC15 server instance> -KeyName DatabaseName -KeyValue "<BC14 database name>"
    ```
    
    In a single tenant deployment, this will mount the tenant automatically. For more information, see [Connecting a Server Instance to a Database](../administration/connect-server-to-database.md).

<!--
2. Configure the server instance to synchronize only the system application objects with tenants.

    This is done by setting the `FeatureSwitchOverrides` parameter to `forceSystemOnlyBaseSync`.

    ```
    Set-NAVServerConfiguration <BC15 server instance> -KeyName "FeatureSwitchOverrides" -KeyValue "forceSystemOnlyBaseSync"
    ```

    This is required in order to synchronize tenants later in the upgrade process. This is required because the application database still contains the old metadata for the C/AL application objects, and these should not be synchronized with the tenant. By making this change, only system objects will by synchronized with the tenant. If you omit this step, you will get conflicts because of duplicate object IDs.
-->
2. Disable task scheduler on the server instance for purposes of upgrade.

    ```
    Set-NavServerConfiguration -ServerInstance <BC15 server instance> -KeyName "EnableTaskScheduler" -KeyValue false
    ```
    Be sure to re-enable this after upgrade if needed.
3. Restart the server instance.

    ```
    Restart-NAVServerInstance -ServerInstance <BC15 server instance>
    ```

## Task 6: Publish system symbols, base application, and test library extensions

In this task, you will publish extensions to the version 15.0 server instance. Publishing an extension adds the extension to the application database that is mounted on the server instance, making it available for installing on tenants later. Publishing updates internal tables, compiles the components of the extension behind-the-scenes, and builds the necessary metadata objects that are used at runtime.

The steps in this task continue to use the [!INCLUDE[adminshell](../developer/includes/adminshell.md)] for version 15.0 that you started in the previous task.

<!--
1. Increase the application version of the application database, and restart the server instance.

    Use the [Set-NAVApplication](/powershell/module/microsoft.dynamics.nav.management/set-navapplication) cmdlet to increase the application version number of the database to the version 15.0 application version.

    ```
    Set-NAVApplication BC150 -ApplicationVersion 15.0.0.0 -force
    ```

    ```
    Restart-NAVServerInstance -ServerInstance BC150
    ```
-->
1. Publish the system symbols extension for version 15.

    The symbols extension contains the required platform symbols that the base application depends on. The symbols extension package is called **System.app**. You find it where the **AL Development Environment** is installed, which by default is C:\Program Files (x86)\Microsoft Dynamics 365 Business Central\150\AL Development Environment.  

    ```
    Publish-NAVApp -ServerInstance <BC15 server instance> -Path "<path to the System.app file>" -PackageType SymbolsOnly
    ```
2. Publish the custom base application extension that you created in **Task 2**.

    ```
    Publish-NAVApp -ServerInstance <BC15 server instance> -Path "<path to the base application extension package file>"
    ```

3. Publish the test library extension if you created one in **Task 2**.

    ```
    Publish-NAVApp -ServerInstance <BC15 server instance> -Path "<path to the test library extension package file>"
    ```

## Task 7: Synchronize tenant and synchronize/install base application and test library extensions

In this task, you update the schema of tenant database schema with schema of changes in system objects and application objects. In this step, you will synchronize the tenant to the to your custom base application extension and test library extension (if any). With this operation, the extensions will take ownership of the tables in the SQL database.

If you have a multitenant deployment, perform these steps for each tenant (replacing `<tenant ID>` with the appropriate tenant ID).

1. (Multitenant only) Mount the tenant to the version 15 server instance.

    To mount the tenant, use the [Mount-NAVTenant](/powershell/module/microsoft.dynamics.nav.management/mount-navtenant) cmdlet:
    
    ```
    Mount-NAVTenant -ServerInstance <BC15 server instance> -DatabaseName "<BC14 database name>" -DatabaseServer <database server>\<database instance> -Tenant <tenant ID> -AllowAppDatabaseWrite
    ```
    
    > [!IMPORTANT]
    > You must use the same tenant ID for the tenant that was used in the old deployment; otherwise you will get an error when mounting or syncing the tenant. If you want to use a different ID for the tenant, you can either use the `-AlternateId` parameter now or after upgrading, dismount the tenant, then mount it again using the new ID and the `OverwriteTenantIdInDatabase` parameter.  
    
    > [!NOTE]  
    > For upgrade, we recommend that you use the `-AllowAppDatabaseWrite` parameter. After upgrade, you can dismount and mount the tenant again without the parameter if needed.

2. Synchronize the tenant to the system objects.
  
    Use the [Sync-NAVTenant](/powershell/module/microsoft.dynamics.nav.management/sync-navtenant) cmdlet:

    ```  
    Sync-NAVTenant -ServerInstance <BC15 server instance> -Tenant <tenant ID> -Mode Sync
    ```
    
    With a single-tenant deployment, you can omit the `-Tenant` parameter and value.

    At this stage, the tenant state is **Operational**.

3. Synchronize the tenant to the base application extension (Base Application).

    Use the [Sync-NAVApp](/powershell/module/microsoft.dynamics.nav.apps.management/sync-navapp) cmdlet:

    ```
    Sync-NAVApp -ServerInstance <BC15 server instance> -Name "Base Application" -Version <extension version> -tenant <tenant ID>
    ```

    With this step, the base app takes ownership of the database tables. When completed, in SQL Server, the table names will be suffixed with the base app extension ID.

4. Install custom base application extension on the tenant.

    To install the extension, you use the [Install-NAVApp cmdlet](/powershell/module/microsoft.dynamics.nav.apps.management/install-navapp). 

    ```
    Install-NAVApp -ServerInstance <BC15 server instance> -Name "Base Application" -Version <extension version>
    ```

    At this point, the base application is upgraded to the version 15 platform and is operational. You should be able to open the application in the client.

5. Synchronize and install the test library extension, like what you did for the custom base application in steps 3 and 4.


## Task 8: Configure the version 15 server instance for migrating extensions

With this task, you configure the version 15 server so that the Microsoft and 3rd party extensions that were installed in the version 14 deployment can be reinstalled. You will do this by configuring the `DestinationAppsForMigration` parameter of the serve instance with information about the custom base application and test library. Specifically, you need the appId, name, and publisher assigned to these extensions. With the `DestinationAppsForMigration` parameter set, when you publish the Microsoft and 3rd party extensions, the server instance will automatically modify the manifest of the extensions to include the dependency on the base application and test library extension, allowing them to be published.

1. Get the appId, name, and publisher of the custom base application and test library extensions.

    ```
    Get-NAVAppInfo -ServerInstance <BC15 server instance>
    ```
2. Set the `DestinationAppsForMigration` parameter for the server instance configuration to include the information about the custom base application and test library (if used). For example:<!-- skip this step for now in single tenant-->

    ```
    Set-NAVServerConfiguration -ServerInstance <BC15 server instance> -KeyName "DestinationAppsForMigration" -KeyValue '[{"appId":"437dbf0e-84ff-417a-965d-ed2bb9650972", "name":"Base Application", "publisher": "Microsoft"},{"appId":"<test library extension app ID>", "name":"<test library extension name>", "publisher": "<test library publisher>"}]'
    ```
3. Restart the server instance.

<!--## Task 8: Publish, Sync and install Microsoft and third party extensions

Upgrading data updates the data that is stored in the tables of the tenant database to the schema changes that have been made to tables in application database and extensions. This step will also automatically install the **System Application** and **Base Application** extensions on the tenant.

1. To run the data upgrade, use the [Start-NavDataUpgrade](/powershell/module/microsoft.dynamics.nav.management/start-navdataupgrade) cmdlet:

    ```
    Start-NAVDataUpgrade -ServerInstance BC150 -Tenant default -FunctionExecutionMode Serial -SkipCompanyInitialization -SkipAppVersionCheck -Force
    ```        
    
    This step upgrades the data and installs the System Application and BaseApp extensions on the tenant. If you do not want to install the extensions, use the `-ExcludeExtensions` parameter. In this, case you will have to manually install these extensions before you complete the next step or to open the application in the client.
    
    > [!TIP]  
    >  In the last phase of data upgrade, all companies will be initialized by running codeunit 2 Company Initialization. This is done automatically. If you want to skip company initialization, then use the `Start-NavDataUpgrade` with the `-SkipCompanyIntitialization` parameter.
    
    To view the progress of the data upgrade, you can run Get-NavDataUpgrade cmdlet with the `–Progress` switch.
    
    When completed, the tenant state should be **Operational**.
2. (Single tenant only) When upgrade is completed, restart the server instance.

    You will see that the custom base application has been installed on the tenant.

The application should now be accessible from the client.-->

## Task 9: Publish, synchronize, and install extensions on the tenants

Now, you can install the Microsoft and 3rd-party extensions that were installed on the tenant before the upgrade.

1. Publish the old extension versions.

    ```
    Publish-NAVApp -ServerInstance <BC15 server instance> -Path "<path to extension package file>"
    ```

    You only need to do this once.

2. Synchronize the extension.

    ```
    Sync-NAVApp -ServerInstance <BC15 server instance> -Name "<extension name>" -Version <extension version> -tenant <tenant ID>
    ```
3. Install the extension:

    ```
    Install-NAVApp -ServerInstance <BC15 server instance> -Name "<extension name>" -Version <extension version> -tenant <tenant ID>
    ```
4. Repeat steps 2 and 3 for each extension and on each tenant.

Now, your application is fully upgraded to the version 15 platform.

## Task 10: Post-upgrade

1. Enable task scheduler on the server instance.
2. (Multitenant only) For tenants other than the tenant that you use for administration purposes, if you mounted the tenants using the `-AllowAppDatabaseWrite` parameter, dismount the tenants, then mount them again without using the `-AllowAppDatabaseWrite` parameter.

## See Also  
[Upgrading the Data](Upgrading-the-Data.md)   
[Upgrading to Business Central](upgrading-to-business-central.md)  
