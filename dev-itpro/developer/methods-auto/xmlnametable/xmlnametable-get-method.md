---
title: "Get Method"
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
# Get Method
Gets the atomized string with the specified value.


## Syntax
```
[Ok := ]  XmlNameTable.Get(Key: String, var Result: Text)
```
## Parameters
*XmlNameTable*  
&emsp;Type: [XmlNameTable](xmlnametable-data-type.md)  
An instance of the [XmlNameTable](xmlnametable-data-type.md) data type.  

*Key*  
&emsp;Type: [String](../string/string-data-type.md)  
The string to find.
        
*Result*  
&emsp;Type: [Text](../text/text-data-type.md)  
The atomized string object if the string has been atomized.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the key exists, otherwise **false**. If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[XmlNameTable Data Type](xmlnametable-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)