---
title: "Company Method"
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
# Company Method
Gets or sets the company property in a SessionSettings object.


## Syntax
```
[Company := ]  SessionSettings.Company([NewCompanyName: String])
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
## Parameters
*SessionSettings*  
&emsp;Type: [SessionSettings](sessionsettings-data-type.md)  
An instance of the [SessionSettings](sessionsettings-data-type.md) data type.  

*NewCompanyName*  
&emsp;Type: [String](../string/string-data-type.md)  
Specifies the name of the company in the SessionSettings object. The company must already exist in the database, otherwise you will get an error at runtime.
        


## Return Value
*Company*  
&emsp;Type: [String](../string/string-data-type.md)  
The name of the company that is set in the SessionSettings object.
        


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks
The company property in the SessionSettings object corresponds to the **Company** field in the in the system table **2000000073 User Personalization**.

## Example
This example creates a SessionSettings object that is populated with the current client user's personalization data, and then calls the COMPANY method to change the company to 'MyCompany'. Finally, the REQUESTSESSIONUPDATE method sends a request to the client to abandon the current session and start a new session that uses the new company. This example requires a SessionSettings data type variable.

```
var
  MySessionSettings : SessionSettings;
begin
  MySessionSettings.INIT;
  MySessionSettings.COMPANY('MyCompany');
  MySessionSettings.REQUESTSESSIONUPDATE(false);
end;  
```  


## See Also
[SessionSettings Data Type](sessionsettings-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)