---
title: "Isolated Storage"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
ms.assetid: b179c72d-48ea-4015-bb76-c60a3b459c70
caps.latest.revision: 21
author: SorenGP
---
# Isolated Storage
Isolated Storage is a data storage that provides isolation between extensions, so that you can keep keys/values in one extension from being accessed from other extensions. Keys/values in the Isolated Storage are accessible through an API. The involved option type is [DataScope Option Type](methods-auto/datascope/datascope-option.md).

The methods supported for IsolatedStorage are:

|Method|Description|For more information, see|  
|--------------|-----------------|-------------------------------|  
|Set(String, String, [DataScope])|Sets the value associated with the specified key within the extension.|[Set(String, String, [DataScope]) Method](methods-auto/isolatedstorage/isolatedstorage-set-method.md)|  
|Get(String, [DataScope], var Text)|Gets the value associated with the specified key within the extension.|[Get(String, [DataScope], var Text) Method](methods-auto/isolatedstorage/isolatedstorage-get-string-datascope-text-method.md)|  
|Contains(String, [DataScope])|Determines whether the storage contains a value with the specified key within the extension.|[Contains(String, [DataScope]) Method](methods-auto/isolatedstorage/isolatedstorage-contains-method.md)|  
|Delete(String, [DataScope])|Deletes the value with the specified key from the isolated storage within the extension.|[ISOLATEDSTORAGE.DELETE Method](methods-auto/isolatedstorage/isolatedstorage-delete-method.md)|
|SetEncrypted(String, String, [DataScope])|Encrypts and sets the value associated with the specified key. The input string cannot exceed a length of 215 plain characters; be aware that special characters take up more space.|[SetEncrypted(String, String, [DataScope]) Method](methods-auto/isolatedstorage/isolatedstorage-setencrypted-method.md)|

## See Also  
[DataScope Option Type](methods-auto/datascope/datascope-option.md)
