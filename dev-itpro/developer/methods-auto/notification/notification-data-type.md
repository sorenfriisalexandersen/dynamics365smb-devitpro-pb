---
title: "Notification Data Type"
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
# Notification Data Type
Provides a programmatic way to send non-intrusive information to the user interface (UI) in the Business Central Web client.



The following methods are available on instances of the Notification data type.

|Method name|Description|
|-----------|-----------|
|[Id([Guid])](notification-id-method.md)|Specifies the identifier for a notification.|
|[AddAction(String, Integer, String)](notification-addaction-method.md)|Specifies an action for the notification.|
|[GetData(String)](notification-getdata-method.md)|Retrieves data that was passed to a notification instance as specified by a SETDATA method call.|
|[Message([String])](notification-message-method.md)|Specifies the content of the notification.|
|[Scope([NotificationScope])](notification-scope-method.md)|Specifies the context in which the notification appears in the client.|
|[Send()](notification-send-method.md)|Sends the notification to the client, where it will display in the UI.|
|[Recall()](notification-recall-method.md)|Recall a sent notification.|
|[SetData(String, String)](notification-setdata-method.md)|Specifies a data property value for the notification. The data is specified as text in a key-value pair.|
|[HasData(String)](notification-hasdata-method.md)|Checks if data was passed to a notification instance as specified by a SETDATA method call.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Notifications](../../devenv-notifications-developing.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  