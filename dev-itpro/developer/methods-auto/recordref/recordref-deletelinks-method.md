---
title: "DeleteLinks Method"
ms.author: solsen
ms.custom: na
ms.date: 10/09/2019
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
# DeleteLinks Method
Deletes all of the links that have been added to a record.


## Syntax
```
 RecordRef.DeleteLinks()
```

## Parameters
*RecordRef*  
&emsp;Type: [RecordRef](recordref-data-type.md)  
An instance of the [RecordRef](recordref-data-type.md) data type.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
 The following example deletes all links from a customer record in the Customer table. The code starts by opening table 18 \(Customer\) as a RecordRef variable that is named CustomerRecref. The [FIELD Method \(RecordRef\)](recordref-field-method.md) creates a FieldRef variable that is named MyFieldRef for the first field in the table \(No.\). `MyFieldRef.VALUE` selects record 01121212 from the No. field. This record is initialized in the CustomerNum variable. The [FIND Method \(RecordRef\)](recordref-find-method.md) searches for record 01121212. If the record is found, the DELETELINKS method deletes all the links in the record. A message that states that the links are deleted is displayed in a message box. You can verify that the links are deleted in the **Links** FactBox on the Customer List or Customer Card pages. 
  
```  
var
    MyFieldRef: FieldRef;
    CustomerRecRef: RecordRef;
    CustomerNUm: Integer;
    Text000: Label 'The link with id %1 is deleted.;
    Text001: Label 'The customer cannot be found.';
begin     
    CustomerNum := '01121212';  
    CustomerRecref.OPEN(18);  
    MyFieldRef := CustomerRecref.FIELD(1);  
    MyFieldRef.VALUE := CustomerNum;  
    if CustomerRecref.FIND('=') then begin  
      CustomerRecref.DELETELINKS;  
      MESSAGE(Text000, CustomerNum);  
    end else
      MESSAGE(Text001);  
end;
```  

## See Also
[RecordRef Data Type](recordref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)