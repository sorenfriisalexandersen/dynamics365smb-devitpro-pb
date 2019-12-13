---
title: "Message Method"
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
# Message Method
Specifies the message that will be sent to telemetry. For a 'Client' error type, the message will also be appear in the client.


## Syntax
```
[Message := ]  ErrorInfo.Message([Message: String])
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
## Parameters
*ErrorInfo*  
&emsp;Type: [ErrorInfo](errorinfo-data-type.md)  
An instance of the [ErrorInfo](errorinfo-data-type.md) data type.  

*Message*  
&emsp;Type: [String](../string/string-data-type.md)  
The message of the the ErrorInfo  


## Return Value
*Message*  
&emsp;Type: [String](../string/string-data-type.md)  
The current message of the ErrorInfo.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[ErrorInfo Data Type](errorinfo-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)