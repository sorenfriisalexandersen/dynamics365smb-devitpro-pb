---
title: "GetModuleInfo Method"
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
# GetModuleInfo Method
Gets information about the specified AL application.


## Syntax
```
[Ok := ]  NavApp.GetModuleInfo(AppId: Guid, var Info: ModuleInfo)
```
## Parameters
*AppId*  
&emsp;Type: [Guid](../guid/guid-data-type.md)  
The ID of the application for which to retrieve information.
        
*Info*  
&emsp;Type: [ModuleInfo](../moduleinfo/moduleinfo-data-type.md)  
A value containing information about the application with the given ID.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the information could be retrieved, otherwise **false**.If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[NavApp Data Type](navapp-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)