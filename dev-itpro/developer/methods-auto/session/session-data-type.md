---
title: "Session Data Type"
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
# Session Data Type
Represents a Microsoft Dynamics Business Central session.


The following methods are available on the Session data type.


|Method name|Description|
|-----------|-----------|
|[ApplicationArea([String])](session-applicationarea-method.md)|Gets or sets the application areas for the current session.|
|[StartSession(var Integer, Integer [, String] [, var Record])](session-startsession-method.md)|Starts a session without a UI and runs the specified codeunit.|
|[IsSessionActive(Integer)](session-issessionactive-method.md)|Tests if the specified SessionID is active on the server instance where it was started.|
|[CurrentExecutionMode()](session-currentexecutionmode-method.md)|Specifies the mode in which the session is running.|
|[StopSession(Integer [, String])](session-stopsession-method.md)|Stops a session.|
|[CurrentClientType()](session-currentclienttype-method.md)|Gets the client type that is running in current session.|
|[DefaultClientType()](session-defaultclienttype-method.md)|Gets the default client that is configured for the server instance that is used by the current session.|
|[BindSubscription(Codeunit)](session-bindsubscription-method.md)|Binds the event subscriber methods in the codeunit to the current codeunit instance for handling the events that they subscribe to. This essentially activates the subscriber functions for the codeunit instance.|
|[UnbindSubscription(Codeunit)](session-unbindsubscription-method.md)|Unbinds the event subscriber methods from in the codeunit instance. This essentially deactivates the subscriber methods for the codeunit instance.|
|[ApplicationIdentifier()](session-applicationidentifier-method.md)|Gets the application ID associated with the current thread.|
|[SendTraceTag(String, String, Verbosity, String [, DataClassification])](session-sendtracetag-method.md)|Send a trace tag to the telemetry service.|
|[EnableVerboseTelemetry(Boolean, Duration)](session-enableverbosetelemetry-method.md)|Temporarily enable verbose telemetry on the current session.|
|[GetExecutionContext()](session-getexecutioncontext-method.md)|Gets the current session's execution context.|
|[GetModuleExecutionContext([Guid])](session-getmoduleexecutioncontext-method.md)|Gets the current session's execution context scoped to a specific module.|
|[GetCurrentModuleExecutionContext()](session-getcurrentmoduleexecutioncontext-method.md)|Gets the current session's execution context for the currently executing module.|


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  