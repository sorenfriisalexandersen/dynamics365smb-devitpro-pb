---
title: "LocaleId Method"
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
# LocaleId Method
Gets or sets the locale ID property in a SessionSettings object.


## Syntax
```
[LocaleId := ]  SessionSettings.LocaleId([NewLocaleId: Integer])
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
## Parameters
*SessionSettings*  
&emsp;Type: [SessionSettings](sessionsettings-data-type.md)  
An instance of the [SessionSettings](sessionsettings-data-type.md) data type.  

*NewLocaleId*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
Specifies the locale ID to set in the SessionSettings object. The value must be a valid Windows locale ID.
        


## Return Value
*LocaleId*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The locale ID that is set in the SessionSettings object.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
The locale ID in the SessionSettings object corresponds to the **Locale ID** field in the system table **2000000073 User Personalization** for the client session user.

## Example
This example creates a SessionSettings object that is populated with the current client user's personalization data, and then uses the LOCALEID method to set the locale ID to '1033'. Finally, the REQUESTSESSIONUPDATE method sends a request to the client to abandon the current client session and start a new session that uses the new locale ID. This example requires a SessionSettings data type variable.

```
var
  MySessionSettings : SessionSettings;
begin
  MySessionSettings.INIT;
  MySessionSettings.LOCALEID(1033);
  MySessionSettings.REQUESTSESSIONUPDATE(false);
end;  
```  


## See Also
[SessionSettings Data Type](sessionsettings-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)