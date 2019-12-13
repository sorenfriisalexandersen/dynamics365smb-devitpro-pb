---
title: "DefaultClientType Method"
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
# DefaultClientType Method
Gets the default client that is configured for the server instance that is used by the current session.


## Syntax
```
ClientType :=   Session.DefaultClientType()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
> [!NOTE]  
> This method can be invoked without specifying the data type name.  


## Return Value
*ClientType*  
&emsp;Type: [ClientType](../clienttype/clienttype-option.md)  
The default client that is configured for the server instance that is used by the current session.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 You can use DEFAULTCLIENTTYPE in a [GETURL Method](../../methods/devenv-geturl-method.md) call to get the URL of the default client.  

## Example  
 In the following example, DEFAULTCLIENTTYPE is used to return the default client type that is configured for the [!INCLUDE[d365fin_server_md](../../includes/d365fin_server_md.md)] instance that is used by the current session.  

```  
if DEFAULTCLIENTTYPE = CLIENTTYPE::Web then  
  Message('The default client is Web client');  
```  

## Example  
 In the following example, DEFAULTCLIENTTYPE is used as a parameter in the GETURL method to return the URL of the default client that is configured for the [!INCLUDE[d365fin_server_md](../../includes/d365fin_server_md.md)] instance.  

```  
url := GETURL(DEFAULTCLIENTTYPE);  
MESSAGE('The URL is %1.', url);  
```  

## See Also
[Session Data Type](session-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)