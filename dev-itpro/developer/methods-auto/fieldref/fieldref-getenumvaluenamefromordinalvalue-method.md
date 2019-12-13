---
title: "GetEnumValueNameFromOrdinalValue Method"
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
# GetEnumValueNameFromOrdinalValue Method
Gets an Enum value (or Option member) name from the Enum metadata for the field that is currently selected.


## Syntax
```
The Enum value name or empty if the ordinal value doesn't exist :=   FieldRef.GetEnumValueNameFromOrdinalValue(Ordinal: Integer)
```
## Parameters
*FieldRef*  
&emsp;Type: [FieldRef](fieldref-data-type.md)  
An instance of the [FieldRef](fieldref-data-type.md) data type.  

*Ordinal*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The Enum value's ordinal value to get the Enum value (or Option member) name for.  


## Return Value
*The Enum value name or empty if the ordinal value doesn't exist*  
&emsp;Type: [String](../string/string-data-type.md)  
The Enum value name.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[FieldRef Data Type](fieldref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)