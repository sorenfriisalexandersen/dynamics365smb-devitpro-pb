---
title: "Run Method"
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
# Run Method
Loads and executes the unit of C/AL code that you specify.


## Syntax
```
[Ok := ]  Codeunit.Run(var Record: Record)
```
## Parameters
*Codeunit*  
&emsp;Type: [Codeunit](codeunit-data-type.md)  
An instance of the [Codeunit](codeunit-data-type.md) data type.  

*Record*  
&emsp;Type: [Record](../record/record-data-type.md)  
A record from the table that is associated with the codeunit.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the operation was successful; otherwise **false**.  If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Codeunit Data Type](codeunit-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)