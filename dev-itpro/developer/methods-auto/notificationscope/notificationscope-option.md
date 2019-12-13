---
title: "NotificationScope System Option"
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
# NotificationScope Option Type
Specifies the context in which the notification appears in the client.

## Members
|  Member  |  Description  |
|----------------|---------------|
|GlobalScope|The notifications are not directly related to the user's current task. **Note:** GlobalScope is currently not supported, so do not use this value.|
|LocalScope|The notification appears in context of the user's current task, on the page the user is currently working on. This is the default value.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  