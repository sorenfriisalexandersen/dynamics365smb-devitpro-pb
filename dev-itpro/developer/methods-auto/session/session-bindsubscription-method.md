---
title: "BindSubscription Method"
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
# BindSubscription Method
Binds the event subscriber methods in the codeunit to the current codeunit instance for handling the events that they subscribe to. This essentially activates the subscriber functions for the codeunit instance.


## Syntax
```
[Ok := ]  Session.BindSubscription(Codeunit: Codeunit)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*Codeunit*  
&emsp;Type: [Codeunit](../codeunit/codeunit-data-type.md)  
The codeunit that contains the event subscribers.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the event subscriber methods bind successfully to the codeunit instance and no errors occurred, otherwise **false**.If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 You can only call this method on codeunits that have the [EventSubscriberInstance Property](../../properties/devenv-eventsubscriberinstance-property.md) set to **Manual**.  
  
 The codeunit instance to which event subscribers bind will be this exact instance and events will be raised on this instance. You cannot bind the same instance more than once, but you can bind multiple instances of the same codeunit. This will result in an event subscriber call on each bound instance when a given event is raised.  
  
## Example  
 The following pseudocode illustrates a typical use of the BINDSUBSCRIPTION method.  
  
```  
Method MyFunction(….)  
LocalVar  
  SubScriberCodeunit5000;  
begin 
  // Set global information on the subscriber codeunit if required  
  // You can rely on the instance being the same as the one receiving the event subscriber call  
  
  SubScriberCodeunit5000.MySetGlobalInfo(<info you can later test in the subscriber event method>)  
  BINDSUBSCRIPTION(SubscriberCodeunit5000);  
  DoSomething(…);  // After binding, all subscriptions on SubscriberCodeunit5000 are “active”.  
  
end; // Notice, that when SubScriberCodeunit5000 goes out of scope, all bindings are removed.  
  
```  
  

## See Also
[Session Data Type](session-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)