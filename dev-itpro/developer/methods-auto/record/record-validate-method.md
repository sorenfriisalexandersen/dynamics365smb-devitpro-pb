---
title: "Validate Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/14/2019
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
# Validate Method
Calls the OnValidate trigger for the field that you specify.


## Syntax
```
 Record.Validate(Field: Any [, NewValue: Any])
```
## Parameters
*Record*  
&emsp;Type: [Record](record-data-type.md)  
An instance of the [Record](record-data-type.md) data type.  

*Field*  
&emsp;Type: [Any](../any/any-data-type.md)  
A field together with associated triggers.
          
*NewValue*  
&emsp;Type: [Any](../any/any-data-type.md)  
The value to insert into Field.
          



[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Record Data Type](record-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)