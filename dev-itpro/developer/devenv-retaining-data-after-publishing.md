---
title: "Synchronizing extension test data"
description: "Retaining table data after publishing an extension"

author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 10/01/2019
ms.topic: article
ms.service: "dynamics365-business-central"
ms.author: solsen
---

# Retaining table data after publishing
When developing an extension, you debug several times using the F5 shortcut key, and you also test your app by adding some sample data every time. To simplify the extension development process in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], you can synchronize the sample data specified in the extension when you do subsequent publishing from Visual Studio Code.

## How data synchronization works
The data synchronization between each publish is controlled by the `schemaUpdateMode` setting, which is specified in the `launch.json` file. This setting consists of three options; **Synchronize**, **Recreate**, and **ForceSync**. 

The default value for `schemaUpdateMode` is set to the **Synchronize** mode, which means that every time you publish an extension to the development server, the data you entered previously stays. If you do not want to synchronize the sample data with each publish, you can change the `schemaUpdateMode` setting from `Synchronize` to, for example, `Recreate` with the syntax shown in the example below.


```json
 { 
     "type": "al",
     "request": "launch",
     "name": "your own server",
     "server": "https://localhost",
     "serverInstance": "Nav",
     "authentcation": "UserPassword", 
     "startupobjectId": 22,
     "schemaUpdateMode": "Recreate" 
 }
```

## Recreate mode
When you set the schema update mode to **Recreate**, all the tables and table extensions are recreated at every publish, which means that all the data in those tables are lost. This means that you will get empty records when you publish your extension.

## ForceSync mode
ForceSync is similar to the existing Synchronize schema update mode, but contains more freedom to make schema changes while retaining data. To enable this mode, set `schemaUpdateMode` to `"ForceSync"`and then set the `"version"` parameter in the app.json file to a fixed number. Data will be preserved in almost all cases with the exception of changing the main table's primary key, in which case the data from the extension tables will be lost. Field renames are allowed and supported in this mode, but the data can only be preserved if you maintain the same ID for the field. If you change both the name and the ID of the field then the data will be lost.

> [!NOTE]  
> This schema update mode is only meant for testing and development and should never be used in production.

In addition to the `launch.json` file setting, the **ForceSync** switch is available through the PowerShell cmdlet `Sync-NavApp –Mode ForceSync`.

## Things to be aware of

**Synchronize** is the default schema update mode for syncing the database and the extension. There are some key factors to consider when you work with the **Synchronize** mode.  

- After publishing, the field data and the primary key information synchronizes with all the tables and the table extensions. This means that you can do additions easily, but not deletions. Breaking changes are never supported in synchronize mode. For example, you can add a field and sync that with the extension just by pressing the F5 shortcut key, but if a field is removed then the table data cannot be synchronized.
If you, during development, for example, discover that you no longer want field **X**, and you then mark field **X** as obsolete, you may still want to write an [upgrade codeunit](devenv-upgrading-extensions.md) to move the data from the obsolete field to a new field **Y** that you introduce. Later, the obsoleted field will not be available. But if you do not want the data, you can choose to use the **Recreate** mode instead.
 
- When you make changes to the data types, you can only *enlarge* the unit size, and *not decrease* the unit size. For example, you can set a text type from `Code[20]` to `Code[50]` or `Text[32]` to  `Text[87]`, and you cannot set a text type from `Code[50]` to `Code[30]` or `Text[87]` to `Text[40]`.  

- Making major table structural changes could lead to compilation errors. For example, if you want to update a primary key. In this case, the table data cannot be synchronized, and if you want to publish the extension, you must change the `schemaUpdateMode` to `Recreate`.  


## See Also
[AL Development Environment](devenv-reference-overview.md)  
[Upgrading Extensions](devenv-upgrading-extensions.md)  
[Debugging](devenv-debugging.md)  
