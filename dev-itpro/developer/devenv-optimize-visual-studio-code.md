---
title: "Optimize Visual Studio Code Editing and Building Performance"
description: "Explains how yo configure Visual Studio Code to get better performance when editing and building AL projects"
author: jswymer
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
ms.author: jswymer
---

# Optimizing Visual Studio Code for AL Development

Visual Studio Code is built to handle many smaller, dependent projects, and not one large project, however, as the base application is not yet split into modules or components that allows managing the code in smaller projects, we recommend the following performance optimizations.

Open your `settings.json` file in the project (or global settings if you prefer that). Set:

- `"al.enableCodeAnalysis": false` to remove code analysis, read more here [Using the Code Analysis Tool](../developer/devenv-using-code-analysis-tool.md).

- `"al.enableCodeActions": false`

- `"editor.codeLens": false` to remove code lens in Visual Studio Code, see [Code Navigation](https://code.visualstudio.com/Docs/editor/editingevolved#_reference-information).

- Add the build folder to the exclusion list for [Windows Defender](https://support.microsoft.com/help/4028485/windows-10-add-an-exclusion-to-windows-security).

## See also 
[Development in AL](devenv-dev-overview.md)   
[Best Practices for AL](../compliance/apptest-bestpracticesforalcode.md)
