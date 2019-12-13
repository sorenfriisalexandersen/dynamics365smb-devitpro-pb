---
title: "FieldIndex Method"
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
# FieldIndex Method
Gets the FieldRef of the field that has this index in the key referred to by the KeyRef variable. Returns an error if no key is selected.


## Syntax
```
Field :=   KeyRef.FieldIndex(Index: Integer)
```
## Parameters
*KeyRef*  
&emsp;Type: [KeyRef](keyref-data-type.md)  
An instance of the [KeyRef](keyref-data-type.md) data type.  

*Index*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The input index.  


## Return Value
*Field*  
&emsp;Type: [FieldRef](../fieldref/fieldref-data-type.md)  
The FieldRef that refers to the field with this index in the key.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 The first field in the index must have index 1, the second index 2, and so on. The last field must have index = FIELDCOUNT. If the index is out of the range supplied or if no table is selected, the method returns an error.  
  
## Example  
 The following example displays the caption of a field in a record. The table with ID 18 \(the Customer table\) is open with a reference. The *Keyref* for the record is retrieved by using the [KEYINDEX Method \(RecordRef\)](../../methods/devenv-keyindex-method-recordref.md). The method retrieves the second key in the record and stores the value in the varKeyRef variable. The varKeyRef variable is then used to return the *FieldRef*. The varFieldRef variable is used to display the caption of the field. 
 
```  
var
    RecRef: RecordRef;
    varKeyRef: KeyRef;
    varFieldRef: FieldRef;
begin  
    RecRef.OPEN(18);  
    varKeyRef := RecRef.KEYINDEX(2);  
    varFieldRef := varKeyRef.FIELDINDEX(1);  
    MESSAGE('The Field name is: %1' ,varFieldRef.CAPTION);  
end;
```  
  

## See Also
[KeyRef Data Type](keyref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)