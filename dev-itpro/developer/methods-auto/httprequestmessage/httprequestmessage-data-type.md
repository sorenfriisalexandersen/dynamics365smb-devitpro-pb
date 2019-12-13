---
title: "HttpRequestMessage Data Type"
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
# HttpRequestMessage Data Type
Represents an HTTP request message.



The following methods are available on instances of the HttpRequestMessage data type.

|Method name|Description|
|-----------|-----------|
|[Content([HttpContent])](httprequestmessage-content-method.md)|Gets or sets the contents of the HTTP message.|
|[Method([String])](httprequestmessage-method-method.md)|Gets or sets the method type as defined in the HTTP standard.|
|[GetRequestUri()](httprequestmessage-getrequesturi-method.md)|Gets the URI used for the HTTP request.|
|[SetRequestUri(String)](httprequestmessage-setrequesturi-method.md)|Sets the URI used for the HTTP request.|
|[GetHeaders(var HttpHeaders)](httprequestmessage-getheaders-method.md)|Gets a reference to the collection of HTTP request headers.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)

> [!NOTE]  
> For performance reasons all HTTP, JSON, TextBuilder, and XML types are reference types, not value types. Reference types holds a pointer to the data elsewhere in memory, whereas value types store its own data. 

## See Also
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  