---
title: How to Alter Databases
description: Modify the Database property settings by using the Alter Database window, which gives you access to the same settings as the New Database window.
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
author: jswymer
---
# Change Collation of an Existing [!INCLUDE[prodshort](../developer/includes/prodshort.md)]

You cannot change the collation directly in the current database. To change the collation, you must create a new database that uses the correct collation, and then export the data from the original database and import it to the new database. You can do this by using SQL Server Management Studio and the [!INCLUDE[adminshell](../developer/includes/adminshell.md)]. 

#### Single-tenant versus multitenant deployment

The process is very similar for single-tenant and multitenant deployments. But there are some differences because a single tenant deployment has one database, but a multitenant deployment has both an application database and a tenant database. In the steps that follow, if you have a single-tenant deployment, consider references to the *application database* and *tenant database* as the same database. When running cmdlets in a single tenant deployment, you can either omit the `-Tenant` parameter or use `default` as the tenant ID.

## Changing the collation if extensions are installed on the tenant

Follow these steps if one or more extensions are installed on the tenant. If there are no installed extensions, you can also use this procedure or the one that follows.

1. Use SQL Server Management Studio to create new databases that are configured to use the desired collation.  

    For a single-tenant deployment, you only have to create one database. For a multitenant deployment, you must create a database for the application and another database for the tenant.

    Make sure that the service account of the [!INCLUDE[server](../developer/includes/server.md)] instance that will connect to the database has proper permission to the database. The service account must be a member of the db\_owner role of the database. For more information see [Provisioning the Microsoft Dynamics NAV Server Account](../deployment/provision-server-account.md).

2. Open the [!INCLUDE[adminshell](../developer/includes/adminshell.md)] as an administrator.

3. Export the application objects, application data, and tenant data from the original database(s) to a `.navdata` type file.

   To export the data, run the [Export-NAVData cmdlet](https://go.microsoft.com/fwlink/?LinkID=401400) as shown in the following example: 

    ```  
    Export-NAVData -ServerInstance <server instance> -Tenant <tenant ID> -IncludeApplication -IncludeApplicationData -IncludeGlobalData -AllCompanies -FilePath <file> 
    ```

    Replace `<file>` with the folder path and name that you want to assign the exported file. The file must have the extension  `.navdata`, for example, `c:\temp\MyDB.navdata`.

    In a multitenant deployment, this export data from the application database and the tenant database into the same file.

4. Import the application objects and application data from the exported file to the new application database.

   To import the data, run the [Import-NAVData cmdlet](https://go.microsoft.com/fwlink/?LinkID=401402) with `-IncludeApplication` and `-IncludeApplicationData` switch parameters. For example:

    ```  
    Import-NAVData -DatabaseServer <database server name> -DatabaseName <new application database name> -IncludeApplication -IncludeApplicationData -FilePath <file>
    ``` 

5. Connect the new application database to the [!INCLUDE[server](../developer/includes/server.md)] instance.  

    ```  
    Set-NAVServerConfiguration <server instance> -KeyName DatabaseName -KeyValue <new application database>
    ```  
    
    For more information, see [Connect a Server Instance to a Database](../administration/connect-server-to-database.md).
     
6.  Restart the server instance.  

    ```  
    Restart-NAVServerInstance -ServerInstance <server instance>
    ```

7. (Multitenant only) Mount the new tenant database to the server instance.

    To mount the tenant, use the [Mount-NAVTenant](/powershell/module/microsoft.dynamics.nav.management/mount-navtenant) cmdlet, for example:

    ```
    Mount-NAVTenant -ServerInstance <server instance> -DatabaseName <new tenant database name> -DatabaseServer <server\instance> -Tenant <tenant ID>
    ```

7.  Synchronize the tenant database with the application.

    To synchronize the database, run the [Sync-NavTenant cmdlet](https://go.microsoft.com/fwlink/?LinkID=401399).

    ```  
    Sync-NAVTenant -ServerInstance <server instance> -Tenant <tenant ID>
    ```

8. Import the tenant data from the exported file to the new tenant database.

    To import the data, run the [Import-NAVData cmdlet](https://go.microsoft.com/fwlink/?LinkID=401402) with `-IncludeGlobalData` and `-AllCompanies` switch parameters. For example:

    ```  
    Import-NAVData -ServerInstance <server instance> -Tenant <tenant ID> -FilePath <file> -IncludeGlobalData -AllCompanies
    ```
9. Synchronize the tenant database with the published extensions.

    To synchronize the database with extensions, use the [Sync-NAVApp](/powershell/module/microsoft.dynamics.nav.apps.management/sync-navapp) cmdlet:

    ```
    Sync-NAVApp -ServerInstance <server instance>  -Tenant <tenant ID> -Name "<extension name>" -Version <version number>
    ```

    If you want to synchronize all published extensions, then you can use the [Get-NAVAppInfo cmdlet](/powershell/module/microsoft.dynamics.nav.apps.management/get-navappinfo), for example:

    ```
    Get-NAVAppInfo -ServerInstance BC140 | % { Sync-NAVApp -ServerInstance BC140 -Name $_.Name -Version $_.Version }
    ```

## Changing the collation if no extensions are installed on the tenant

1. In SQL Server Management Studio, create a new database that uses the desired collation.  

    Make sure that the service account of the [!INCLUDE[server](../developer/includes/server.md)] instance that will connect to the database has proper permission to the database. The service account must be a member of the db\_owner role of the database. For more information see [Provisioning the Microsoft Dynamics NAV Server Account](../deployment/provision-server-account.md).  

2. Export the application objects, application data, and tenant data from the original database to a `.navdata` type file.

   To export the data, run the [Export-NAVData cmdlet](https://go.microsoft.com/fwlink/?LinkID=401400) as shown in the following example: 

    ```  
    Export-NAVData -DatabaseServer <database server name> -DatabaseName <original database name> -IncludeApplication -IncludeApplicationData -IncludeGlobalData -AllCompanies -FilePath c:\temp\MyDB.navdata  
    ``` 

3. Import the data from the original database to the new application database, run the Import-NAVData cmdlet as shown in the following example.  

    ```  
    Import-NAVData -DatabaseServer DatabaseServerName -DatabaseName NewDatabaseName -IncludeApplication -IncludeApplicationData -IncludeGlobalData -AllCompanies -FilePath c:\temp\MyDB.navdata  
    ```  

    For more information, see [Import-NAVData cmdlet](https://go.microsoft.com/fwlink/?LinkID=401402).  

4. Connect the new database to the [!INCLUDE[server](../developer/includes/server.md)] instance.  

    For more information, see [Connect a Server Instance to a Database](../administration/connect-server-to-database.md). 

5. Restart the [!INCLUDE[server](../developer/includes/server.md)] instance.  

6. Synchronize the database. 

    From the [!INCLUDE[adminshell](../developer/includes/adminshell.md)], run the [Sync-NavTenant cmdlet](https://go.microsoft.com/fwlink/?LinkID=401399).

    ```  
    Sync-NAVTenant -ServerInstance <server instance>
    ```

## See Also  
[Creating and Altering a  Database](cside-create-databases.md)  
[Synchronizing the Tenant Database with the Application Database](../administration/synchronize-tenant-database-and-application-database.md)
