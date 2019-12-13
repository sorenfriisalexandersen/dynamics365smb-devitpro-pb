---
title: "Current Method"
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
# Current Method
Gets the current value from the number sequence, without doing any increment. The value is retrieved out of transaction. The value will not be returned on transaction rollback.


## Syntax
```
Current :=   NumberSequence.Current(Name: String [, CompanySpecific: Boolean])
```
## Parameters
*Name*  
&emsp;Type: [String](../string/string-data-type.md)  
Specifies the name of the number sequence.  
*CompanySpecific*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
Specifies if the number sequence is company-specific. Default is true.  


## Return Value
*Current*  
&emsp;Type: [BigInteger](../biginteger/biginteger-data-type.md)  
Returns the current value from number sequence.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example
The following example gets the current value for the number sequence `MyNumberSequence`, which is not company specific.
 
```
number := NumberSequence.Current('MyNumberSequence', false);
```

## See Also
[NumberSequence Data Type](numbersequence-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
