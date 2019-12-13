---
title: "Creating Filter Pages for Filtering Tables"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: jswymer
---
# Creating Filter Pages for Filtering Tables

In AL code, you can use the FILTERPAGEBUILDER data type to create a filter page that enables users to set filters on multiple tables. Filter pages contain one or more filter controls, where each filter control can be used to set filters on a specific table. In the [!INCLUDE[prodshort](includes/prodshort.md)] client, filter pages are generated at runtime and run in a modal dialog box. The following figure illustrates a filter page that filters on the **Item** table.  
  
 ![Shows a filter page for the item table](media/Filter-Page.png "FilterPage")  
  
To create a filter page, you use AL code and the methods that are available for the [FILTERPAGEBUILDER data type](methods-auto/filterpagebuilder/filterpagebuilder-data-type.md). The following code example shows the code that creates the filter page in the figure.  
  
```  
var
    varFilterPageBuilder: FilterPageBuilder;
    varItem: Record Item;
begin
    varFilterPageBuilder.AddTable('Customer Table', DATABASE::Customer);
    varFilterPageBuilder.AddRecord('Item Table', varItem);
    varFilterPageBuilder.Addfield('Item Table', varItem."No.", '>100');
    varFilterPageBuilder.PageCaption := 'Customer and Item Filter Page';
    varFilterPageBuilder.RunModal();
end;
```
  
## See Also

[FILTERPAGEBUILDER data type](methods-auto/filterpagebuilder/filterpagebuilder-data-type.md)  
