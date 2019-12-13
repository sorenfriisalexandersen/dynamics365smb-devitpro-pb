---
title: "FieldCount Method"
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
# FieldCount Method
Gets the number of fields that have been defined in a key. Returns an error if no key is selected.


## Syntax
```
No :=   KeyRef.FieldCount()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*KeyRef*  
&emsp;Type: [KeyRef](keyref-data-type.md)  
An instance of the [KeyRef](keyref-data-type.md) data type.  

## Return Value
*No*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The number of fields that have been defined in the key.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
 The following example retrieves the number of fields that are defined in a key in record. The table with ID 18 \(the Customer table\) is open with a reference to table 18. The [KEYINDEX Method \(RecordRef\)](../../methods/devenv-keyindex-method-recordref.md) method retrieves the second key in the record and store the *KeyRef* in the varKeyRef variable. The [FIELDCOUNT Method \(KEYREF\)](../../methods/devenv-fieldcount-method-keyref.md) is then used to return the number of fields defined in the key and displayed in a message box.
 
```  
var
    RecRef: RecordRef;
    varKeyRef: KeyRef;
    VarCount: Integer;
begin 
    RecRef.OPEN(18);  
    varKeyRef := RecRef.KEYINDEX(2);  
    VarCount := varKeyRef.FIELDCOUNT;  
    MESSAGE('The number of fields defined in the key is: %1', VarCount);  
end;
```  
  

## See Also
[KeyRef Data Type](keyref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)