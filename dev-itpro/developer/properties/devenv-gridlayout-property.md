---
title: "GridLayout Property"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
ms.assetid: 096dd046-161f-4d06-8212-0804f4271590
caps.latest.revision: 13
author: SusanneWindfeldPedersen
---

 

# GridLayout Property
The controls inside this definition should be layed out as a grid using the caption of the first group as row caption. 

## Applies To  
  
-   Group controls on pages  
  
## Property Values  
-   Rows 

-   Columns  

## Syntax
```
GridLayout = Columns;
```
  
## Remarks 

By default, fields in a FastTab on a page are arranged automatically in two columns that are based on the number of fields. You use a Grid control to customize the arrangement of fields into rows and columns, and design it to look like a grid-like format or a matrix-like format. For more information, see [Arranging Fields in Rows and Columns Using the Grid Control](../devenv-arrange-fields-in-rows-and-columns-using-gridlayout-control.md).
 
This property is only supported on grids.

> [!IMPORTANT]
> Arranging in rows only works in the [!INCLUDE[nav_windows_md](../includes/nav_windows_md.md)]. In the [!INCLUDE[webclient](../includes/webclient.md)], fields can only be arranged in columns.

## See Also

[Field Arrangement on FastTabs](../devenv-arranging-fields-on-fasttab.md)  
[Properties](devenv-properties.md)