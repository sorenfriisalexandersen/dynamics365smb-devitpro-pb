---
title: "GetRange Method"
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
# GetRange Method
Get a shallow copy of a range of elements in the source.


## Syntax
```
Result :=   List.GetRange(Index: Integer, Count: Integer)
```
## Parameters
*List*  
&emsp;Type: [List](list-data-type.md)  
An instance of the [List](list-data-type.md) data type.  

*Index*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The one-based List index at which the range starts.
        
*Count*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The number of elements in the range.  


## Return Value
*Result*  
&emsp;Type: [List of [T]](list-data-type.md)  
A shallow copy of a range of elements in the source List.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[List Data Type](list-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)