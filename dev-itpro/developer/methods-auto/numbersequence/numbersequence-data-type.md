---
title: "NumberSequence Data Type"
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
# NumberSequence Data Type
Is a complex data type for creating and managing number sequences in the database.

The following methods are available on the NumberSequence data type.


|Method name|Description|
|-----------|-----------|
|[Insert(String [, BigInteger] [, BigInteger] [, Boolean])](numbersequence-insert-method.md)|Creates a number sequence in the database, with the given parameters.|
|[Exists(String [, Boolean])](numbersequence-exists-method.md)|Checks whether a specific number sequence exists.|
|[Delete(String [, Boolean])](numbersequence-delete-method.md)|Deletes a specific number sequence.|
|[Next(String [, Boolean])](numbersequence-next-method.md)|Retrieves the next value from the number sequence.|
|[Current(String [, Boolean])](numbersequence-current-method.md)|Gets the current value from the number sequence, without doing any increment. The value is retrieved out of transaction. The value will not be returned on transaction rollback.|


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  
