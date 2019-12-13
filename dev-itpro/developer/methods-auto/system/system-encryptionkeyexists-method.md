---
title: "EncryptionKeyExists Method"
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
# EncryptionKeyExists Method
Checks whether an encryption key for the current tenant is present on the server tenant.


## Syntax
```
Ok :=   System.EncryptionKeyExists()
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)


## Example  
 This code example performs checks to determine if an encryption key already exists.  

```  
if ENCRYPTIONENABLED then  
        if ENCRYPTIONKEYEXISTS then  
          MESSAGE('Encryption has been enabled and the encryption key is present in this server instance')  
        else  
          MESSAGE('Encryption has been enabled but the encryption key is not present on this server instance')  
else  
  MESSAGE('Encryption has not been enabled');  
``` 

## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)