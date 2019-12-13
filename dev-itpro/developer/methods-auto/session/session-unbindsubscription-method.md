---
title: "UnbindSubscription Method"
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
# UnbindSubscription Method
Unbinds the event subscriber methods from in the codeunit instance. This essentially deactivates the subscriber methods for the codeunit instance.


## Syntax
```
[Ok := ]  Session.UnbindSubscription(Codeunit: Codeunit)
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
**true** if the event subscriber methods unbind successfully to the codeunit instance and no errors occurred, otherwise **false**.If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 You can only call this method on codeunits that have the [EventSubscriberInstance Property](../../properties/devenv-eventsubscriberinstance-property.md) set to **Manual**.  
  
 Calling this method on a codeunit that has not been bound \(by the [BINDSUBSCRIPTION Method](../../methods-auto/session/session-bindsubscription-method.md)\) will result in an error. If the call to this method is successfull, all bindings are removed.  
  
 The codeunit instance that is unbound will be the same instance that previously was bound.  
  
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
  UNBINDSUBSCRIPTION(SubscriberCodeunit888);  // Now deactivating again  
  DoStuff(…);  // This time no events are raised inside SubscriberCodeunit888;  
  
end;  
  
```  

## See Also
[Session Data Type](session-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)