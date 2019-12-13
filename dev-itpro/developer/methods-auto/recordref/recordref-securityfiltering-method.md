---
title: "SecurityFiltering Method"
ms.author: solsen
ms.custom: na
ms.date: 10/09/2019
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
# SecurityFiltering Method
Gets or sets how security filters are applied to the RecordRef.


## Syntax
```
[SecurityFiltering := ]  RecordRef.SecurityFiltering([NewSecurityFiltering: SecurityFilter])
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
## Parameters
*RecordRef*  
&emsp;Type: [RecordRef](recordref-data-type.md)  
An instance of the [RecordRef](recordref-data-type.md) data type.  

*NewSecurityFiltering*  
&emsp;Type: [SecurityFilter](../securityfilter/securityfilter-option.md)  
The new security filter for the RecordRef.  


## Return Value
*SecurityFiltering*  
&emsp;Type: [SecurityFilter](../securityfilter/securityfilter-option.md)  
The security filter applied to the RecordRef.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[RecordRef Data Type](recordref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)