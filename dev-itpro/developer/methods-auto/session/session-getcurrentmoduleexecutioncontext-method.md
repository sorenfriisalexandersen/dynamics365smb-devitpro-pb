---
title: "GetCurrentModuleExecutionContext Method"
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
# GetCurrentModuleExecutionContext Method
Gets the current session's execution context for the currently executing module.


## Syntax
```
ExecutionContext :=   Session.GetCurrentModuleExecutionContext()
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  


## Return Value
*ExecutionContext*  
&emsp;Type: [ExecutionContext](../executioncontext/executioncontext-option.md)  
The current session's execution context for the currently executing module.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Session Data Type](session-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)