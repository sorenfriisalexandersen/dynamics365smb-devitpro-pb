---
title: "Headers Method"
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
# Headers Method
Gets the HTTP response's HTTP headers.


## Syntax
```
Headers :=   HttpResponseMessage.Headers()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*HttpResponseMessage*  
&emsp;Type: [HttpResponseMessage](httpresponsemessage-data-type.md)  
An instance of the [HttpResponseMessage](httpresponsemessage-data-type.md) data type.  

## Return Value
*Headers*  
&emsp;Type: [HttpHeaders](../httpheaders/httpheaders-data-type.md)  
The HTTP headers.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[HttpResponseMessage Data Type](httpresponsemessage-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)