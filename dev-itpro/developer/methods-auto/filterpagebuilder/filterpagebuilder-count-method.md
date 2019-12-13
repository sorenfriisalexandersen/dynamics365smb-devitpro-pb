---
title: "Count Method"
ms.author: solsen
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: SusanneWindfeldPedersen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# Count Method
Gets the number of filter controls that are specified in the FilterPageBuilder object instance.


## Syntax
```
Count :=   FilterPageBuilder.Count()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*FilterPageBuilder*  
&emsp;Type: [FilterPageBuilder](filterpagebuilder-data-type.md)  
An instance of the [FilterPageBuilder](filterpagebuilder-data-type.md) data type.  

## Return Value
*Count*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The number of filter controls in the current FilterPageBuilder object instance.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
 The following example uses the COUNT method on a filter page object that includes a two filter controls for the **Date** system table.  
 
```
var
    varDateItem: Text[30];  
    varCount: Integer;  
    varFilterPageBuilder: FilterPageBuilder;

begin 
    varDateItem := 'Date record';  
    varFilterPageBuilder.ADDTABLE(varDateItem + ' 1',DATABASE::Date);  
    varFilterPageBuilder.ADDTABLE(varDateItem + ' 2',DATABASE::Date);  
    varCount := varFilterPageBuilder.COUNT;  
    if varCount <> 2 then   
      ERROR('There should be two controls in varFilterPageBuilder');
    varFilterPageBuilder.RunModal();  
end; 
```  

## See Also
[FilterPageBuilder Data Type](filterpagebuilder-data-type.md)  
[Creating Filter Pages for Tables](../../devenv-filter-pages-for-filtering-tables.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)