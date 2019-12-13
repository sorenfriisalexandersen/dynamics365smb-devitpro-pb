---
title: Install a cumulative update
description: This article describes the tasks required for getting the monthly cumulative update applied to your Dynamics 365 Business Central on-premises.
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: jswymer
ms.service: "dynamics365-business-central"
author: jswymer
---
# Installing a [!INCLUDE[prodshort](../developer/includes/prodshort.md)] Spring 2019 Cumulative Update

This article describes how to install a cumulative update for [!INCLUDE[prodshort](../developer/includes/prodshort.md)] on-premises. A cumulative update is a cumulative set of files that includes all hotfixes and regulatory features that have been released for Business Central.

## Download the cumulative update package

The first thing to do is to download the Cumulative Update package that matches your Business Central deployment.

1. Go to the relevant list of available updates for your on-premises version of Business Central, and then choose the Cumulative Update that you want.

    For a list of supported versions of Business Central on-premises, see the [See Also](#see-also) section.
2. From the cumulative update page, under the **Resolution** section, select the link for downloading the update and follow the instructions.
3. On the computer where you downloaded cumulative update, extract files from all .zip files.

The cumulative update includes files that are separated into the following folders:
- APPLICATION folder
  
    Used for updating your application with the new or modified application objects that comprise the cumulative update.
- DVD

    Contains the full Business Central product, including the Business Central installation program (setup.exe) and tools for upgrading to the platform.

When this step is completed, you can proceed to update your Business Central deployment to the new platform and application.

## Update the platform

The following components are part of the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] platform:

- [!INCLUDE[webserver](../developer/includes/webserver.md)]
- [!INCLUDE[server](../developer/includes/server.md)]
- SQL Server components
- [!INCLUDE[nav_windows_md](../developer/includes/nav_windows_md.md)]

To upgrade to the latest platform the database must be converted by using the Dynamics NAV Development Environment.

1. (Single-tenant deployment only) Uninstall all extensions. 

    If the [!INCLUDE[server](../developer/includes/server.md)] is configured as a single-tenant instance, you must uninstall all extensions from tenant. For example, using the [Uninstall-NAVApp cmdlet](/powershell/module/microsoft.dynamics.nav.apps.management/uninstall-navapp) from the [!INCLUDE[adminshell](../developer/includes/adminshell.md)], you can run the following command:

    ```
    Get-NAVAppInfo -ServerInstance <ServerInstanceName> -Tenant default | % { Uninstall-NAVApp -ServerInstance <ServerInstanceName> -Name $_.Name -Version $_.Version }
    ``` 
1. Install Business Central components of the cumulative update.

    From the DVD folder, run setup.exe to install Business Central. As a minimum, install the following components: Server, Web Server Components, SQL Server Components, and the Dynamics NAV Development Environment. For more information, see [Installing Business Central Using Setup](../deployment/install-using-setup.md).
3. Start the new [!INCLUDE[nav_dev_short_md](../developer/includes/nav_dev_short_md.md)] as an administrator
4. Open the application database.

    For more information, see [Open a Database](../cside/cside-open-database.md).
5. If prompted, follow instructions to convert it to the new platform.
6. (Multitenant deployment only) Mount an old tenant to the Business Central Server instance.

    You will have to do this step and the next for each tenant. For more information, see [Mount or Dismount a Tenant](../administration/mount-dismount-tenant.md).
 
7. Synchronize the database (tenant).

    For more information about syncing, see [Synchronizing the Tenant Database and Application Database](../administration/synchronize-tenant-database-and-application-database.md).

## Update the application

The APPLICATION folder includes the following files:
- AccumulatedChangeLog.<Locale>.<Build No.>.txt
- Changelog.<Locale>.<Build No.>.txt
- CUObjects.<Locale>.<Build No.>.fob
- Objects.<Locale>.Objects.<Locale>.<Build No.>.txt

Using [!INCLUDE[nav_dev_long_md](../developer/includes/nav_dev_long_md.md)] for [!INCLUDE[prodshort](../developer/includes/prodshort.md)], complete one of the following tasks.

> [!NOTE]
> If a license update is required for a regulatory feature, customers can download an updated license from CustomerSource (see [How to Download a Microsoft Dynamics 365 Business Central License from CustomerSource](https://mbs.microsoft.com/customersource/documentation/howtodocuments/downloadnavlicensecs.htm)), and partners can download their customers' updated license from VOICE (see [How to Download a Microsoft Dynamics 365 Business Central Customer License from VOICE](https://mbs.microsoft.com/partnersource/deployment/documentation/howtoarticles/howtodownloadcustomernavlicense.htm)).

### Update an unmodified application to the Business Central cumulative update objects

1. Open the database in the [!INCLUDE[nav_dev_short_md](../developer/includes/nav_dev_short_md.md)].
2. Import the CUObjects.<Locale>.<Build No.>.fob  into the application database.

    For more information, see [Importing Objects](../cside/cside-import-objects.md).
3. Replace the existing objects in the database with the cumulative update objects.

### Update a modified application to the Business Central cumulative update objects

1. Import the CUObjects.<Locale>.<Build No.>.fob into the application database.

    For more information, see [Importing Objects](../cside/cside-import-objects.md).
2. When prompted, open the **Import Worksheet**, and review the information.
    1. Replace objects in the database that have NOT been modified.
    2. If a table in the cumulative update has a new field and the same table in your database has been modified, use the **Merge: Existing<-New** or **Merge: New<-Existing** option in the **Import Worksheet** to import the new fields.
    3. For other objects that have been modified, use the CUObjects.<Locale>.<Build No.>.txt file to compare and merge the cumulative update objects with the objects in your database.

        For more information about the worksheet, see [Import Worksheet](../cside/cside-import-worksheet.md).

        > [!NOTE]
        > If you do not want to use the Worksheet, you can use the Changelog.<Locale>.<Build No.>.txt file to manually apply the changes to the objects in your database.

### Updating from [!INCLUDE[prodshort](../developer/includes/prodshort.md)] October 2018 DE Cumulative Update 2 or earlier

Starting with Cumulative Update 03, the ELSTER local functionality is contained in an extension instead of the base application. If you want the latest updates to the ELSTER functionality, you will have to publish and install the extension, which is explained later in this article. To prepare for this, delete the following objects from the application database: page 11016, page 11017, page 11019, and report 11016. These objects will be replaced by the ELSTER extension.

Make sure you synchronize the tenant after you delete the objects.

### Set the application version of database to the application version of the cumulative update

You must increase the application version of the application database in order to perform a data upgrade. We recommend that you change to the application version to that of the cumulative update. You can get this version from the cumulative update release page. For more information, see [Version numbers in Business Central](../administration/version-numbers.md).  

To set the application version, use the [Set-NAVApplication](/powershell/module/microsoft.dynamics.nav.management/set-navapplication) cmdlet of the [!INCLUDE[adminshell](../developer/includes/adminshell.md)] to set the application version as follows:

```powershell
Set-NAVApplication -ServerInstance <ServerInstanceName> -ApplicationVersion Major.CU.ApplicationBuild.Revision -Force
```

### Synchronize and upgrade tenants

1. (Multitenant deployment only) Mount the tenant.

    For more information, see [Mount or Dismount a Tenant ](../administration/mount-dismount-tenant.md).
2. Synchronize the tenant.

3. Run a data upgrade.

    Run [Start-NavDataUpgrade](/powershell/module/microsoft.dynamics.nav.management/start-navdataupgrade) cmdlet of the [!INCLUDE[adminshell](../developer/includes/adminshell.md)]:
    
    ```powershell
    Start-NavDataUpgrade -ServerInstance <ServerInstanceName> -Tenant <TenantID>
    ```

    Replace `<TenantID>` with the tenant ID of the database. If you do not have a multitenant server instance, use `default` or omit this parameter.
  
##  <a name="AddExtensions"></a>Publish and install/upgrade extensions

Complete this task if you are updating:

- A [!INCLUDE[prodshort](../developer/includes/prodshort.md)] October 2018 DE version earlier than Cumulative Update 3 and you want the latest updates to the Elster functionality. Use this procedure to install the following extension:

    |Name|Extension package|
    |----|---------|
    |ELSTER VAT Localization for Germany| Elster.app|
- A [!INCLUDE[prodshort](../developer/includes/prodshort.md)] application that uses extensions.

    The [!INCLUDE[prodshort](../developer/includes/prodshort.md)] installation media (DVD) includes several new versions of Microsoft extensions (that is, extensions that have **Microsoft** as the publisher). If your old deployment uses these extensions, you have to upgrade the current versions to the new versions.

    In addition, other extensions used in the old deployment that you still want to use must be repaired to work on the new platform.

The general steps for this task are listed below. For detailed steps, see [Publishing, Upgrading, and Installing Extensions During Upgrade](upgrade-publish-extensions.md) .

1. Publish new system, test and application symbols.

    You should unpublish the old versions first.
2. Publish the new extension versions from the DVD.
    
    This includes new versions of Microsoft extensions that you already have used on your application, and the ELSTER app for the DE version. The new extension versions are found in the `\Extensions` folder of the installation media (DVD).

3. Synchronize the tenant database with the schema changes of the extensions.

4. Upgrade the data associated with the Microsoft extensions. This is not required the first time you publish the ELSTER extension.

5. Install the newly published extensions on tenants. 

6. Repair, synchronize, and install any custom extensions (third-party) that are currently published and that you still want to use.

    This ensures that the extensions work on the new platform and application versions.

## See Also

[Dynamics 365 Business Central On-Premises October'18 Updates](../deployment/update-versions-13.md)  
[Dynamics 365 Business Central On-Premises April'19 Updates](../deployment/update-versions-14.md)  
[Upgrading the Application Code](Upgrading-the-Application-Code.md)  
[Upgrading to Business Central](upgrading-to-business-central.md)  
[Synchronizing the Tenant Database and Application Database](../administration/synchronize-tenant-database-and-application-database.md)  
[Version numbers in Business Central](../administration/version-numbers.md)  
[Publish and Install an Extension](../developer/devenv-how-publish-and-install-an-extension-v2.md)  