---
title: "ReasonPhrase Method"
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
# ReasonPhrase Method
Gets the reason phrase which typically is sent by servers together with the status code.


## Syntax
```
ReasonPhrase :=   HttpResponseMessage.ReasonPhrase()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*HttpResponseMessage*  
&emsp;Type: [HttpResponseMessage](httpresponsemessage-data-type.md)  
An instance of the [HttpResponseMessage](httpresponsemessage-data-type.md) data type.  

## Return Value
*ReasonPhrase*  
&emsp;Type: [String](../string/string-data-type.md)  
The reason phrase sent by the server.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[HttpResponseMessage Data Type](httpresponsemessage-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)