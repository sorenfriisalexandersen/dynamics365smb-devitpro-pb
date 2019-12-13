---
title: "Dialog Data Type"
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
# Dialog Data Type
Represents a dialog window.


The following methods are available on the Dialog data type.


|Method name|Description|
|-----------|-----------|
|[Error(String [, Any,...])](dialog-error-string-joker-method.md)|Displays an error message and ends the execution of AL code.|
|[Error(ErrorInfo)](dialog-error-errorinfo-method.md)|Displays an error message and ends the execution of AL code.|
|[Message(String [, Any,...])](dialog-message-method.md)|Displays a text string in a message window.|
|[Confirm(String [, Boolean] [, Any,...])](dialog-confirm-method.md)|Creates a dialog box that prompts the user for a yes or no answer. The dialog box is centered on the screen.|
|[StrMenu(String [, Integer] [, String])](dialog-strmenu-method.md)|Creates a menu window that displays a series of options.|

The following methods are available on instances of the Dialog data type.

|Method name|Description|
|-----------|-----------|
|[Open(String [, var Any,...])](dialog-open-method.md)|Opens a dialog window.|
|[Update([Integer] [, Any])](dialog-update-method.md)|Updates the value of a '#'-or '@' field in the active window.|
|[Close()](dialog-close-method.md)|Closes a dialog window that has been opened by the OPEN method.|
|[HideSubsequentDialogs([Boolean])](dialog-hidesubsequentdialogs-method.md)|Specifies that subsequent child dialogs are not shown.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  