---
title: "Insert Method"
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
# Insert Method
Inserts the value at the given index in the array while shifting all the values to the right by one position.


## Syntax
```
[Ok := ]  JsonArray.Insert(Index: Integer, Value: JsonObject)
```
## Parameters
*JsonArray*  
&emsp;Type: [JsonArray](jsonarray-data-type.md)  
An instance of the [JsonArray](jsonarray-data-type.md) data type.  

*Index*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
  
*Value*  
&emsp;Type: [JsonObject](../jsonobject/jsonobject-data-type.md)  
  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the read was successful; otherwise, **false**.If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[JsonArray Data Type](jsonarray-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)