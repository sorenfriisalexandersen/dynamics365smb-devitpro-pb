---
title: "Sleep Method"
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
# Sleep Method
Returns control to the operating system for a specified time.


## Syntax
```
 System.Sleep(Duration: Integer)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*Duration*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The number of milliseconds to return control to the operating system.  



[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 When you use the SLEEP method, control is guaranteed to return to the operating system for at least *Duration* milliseconds.  
  
> [!NOTE]  
>  The period may be longer than *Duration* milliseconds, depending on what the operating system is doing at the time that control is to return to the caller.  
  
  
## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)