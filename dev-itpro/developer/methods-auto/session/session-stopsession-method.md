---
title: "StopSession Method"
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
# StopSession Method
Stops a session.


## Syntax
```
[Ok := ]  Session.StopSession(SessionId: Integer [, Comment: String])
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*SessionId*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The ID of the session that you want to stop.The session can be any of the following:
-   Windows client session
-   Web client session
-   NAS services session
-   SOAP web services client session
-   OData web services client session
-   Background session
          
*Comment*  
&emsp;Type: [String](../string/string-data-type.md)  
An optional comment about the session event. The comment is stored in Table 2000000111, the Session Event table.
          


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the operation was successful; otherwise **false**.  If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 The session that you want to stop and the session that calls STOPSESSION must be running on the same instance of [!INCLUDE[d365fin_server_md](../../includes/d365fin_server_md.md)]. The session is stopped before the next AL statement executes. Open transactions are rolled back.  

> [!NOTE]  
>  If the current executing statement is the **SLEEP** method, then the session is stopped immediately.  

 When a session is executing AL that does not interact with the server connection or the access lock used by the connection, STOPSESSION cannot terminate the connection. STOPSESSION can terminate connections that are inactive, idle, or using the database but not blocked.  

 You cannot stop the current, active session in which you are executing the **STOPSESSION** call.  

## Example  
 This example assumes that you have a table named CacheStressTest that you use for testing.  

```
var
    CacheStressTestRec: Record Customer;
    SessionID: Integer;
begin
    STARTSESSION(SessionId, CODEUNIT::"Cache Stress Test", COMPANYNAME, CacheStressTestRec);  
    STOPSESSION(SessionId, 'Logoff cache stress test session');  
end;

```

## See Also
[Session Data Type](session-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)