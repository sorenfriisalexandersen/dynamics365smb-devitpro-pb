---
title: "Dependencies Method"
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
# Dependencies Method
Gets the collection of application dependencies.


## Syntax
```
Dependencies :=   ModuleInfo.Dependencies()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*ModuleInfo*  
&emsp;Type: [ModuleInfo](moduleinfo-data-type.md)  
An instance of the [ModuleInfo](moduleinfo-data-type.md) data type.  

## Return Value
*Dependencies*  
&emsp;Type: [List of [ModuleDependencyInfo]](../list/list-data-type.md)  
Collection of application dependencies.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[ModuleInfo Data Type](moduleinfo-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)