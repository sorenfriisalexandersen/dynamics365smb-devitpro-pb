---
title: "SetPosition Method"
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
# SetPosition Method
Sets the fields in a primary key on a record to the values specified in the String parameter. The remaining fields are not changed.


## Syntax
```
 RecordRef.SetPosition(String: String)
```
## Parameters
*RecordRef*  
&emsp;Type: [RecordRef](recordref-data-type.md)  
An instance of the [RecordRef](recordref-data-type.md) data type.  

*String*  
&emsp;Type: [String](../string/string-data-type.md)  
The string that is used to set the primary key. This string contains the primary key value to set.  



[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method works the same as the [SETPOSITION Method \(Record\)](../../methods/devenv-setposition-method-record.md).  
  
## Example  
 The following example changes the value in the primary key, the No. field, in table 23 \(Vendor\). Other fields are not changed. The code starts by opening table 23 \(Vendor\) as a RecordRef variable that is named MyRecordRef. The [FIELD Method \(RecordRef\)](recordref-field-method.md) selects the first field \(No.\) and stores the value in the MyFieldRef variable. The [SETFILTER Method \(FieldRef\)](../fieldref/fieldref-setfilter-method.md) sets a filter that selects records from 10000 to 20000. The [FINDLAST Method \(RecordRef\)](recordref-findlast-method.md) finds and retrieves the last record in the record set. The SETPOSITION method changes the value in the No. field from 20000 to 20001. The record No. and the name of the record are displayed before and displayed again after the primary key value is changed. The string that contains the new primary key is initialized in the InputString variable. 
 
```  
var
    MyRecordRef: RecordRef;
    InputString: Text;
    MyFieldRef: FieldRef;
    Text000: Label 'The record No. before the primary key was changed is %1.\\ The vendor name before the primary key was changed is %2.';
    Text001: Label 'The record No. after the primary key was changed is %1. \\ The vendor name after the primary key was changed is %2';
begin   
    InputString := 'No.=CONST(20001)';  
    MyRecordRef.OPEN(23);  
    MyFieldRef := MyRecordRef.FIELD(1);  
    MyFieldRef.SETFILTER('10000..20000');  
    MyRecordRef.FINDLAST;  
    MESSAGE(Text000, MyRecordRef.RECORDID, MyRecordRef.FIELD(2));  
    MyRecordRef.SETPOSITION(InputString);  
    MESSAGE(Text001, MyRecordRef.RECORDID, MyRecordRef.FIELD(2));  
end;
  
```  
  
 The following is displayed before the SETPOSITION method is called:  
  
 **The record No. before the primary key was changed is Vendor: 20000.**  
  
 **The vendor name before the primary key was changed is AR Day property Management.**  
  
 The following is displayed after the SETPOSITION method is called:  
  
 **The record No. after the primary key was changed is Vendor: 20001.**  
  
 **The vendor name after the primary key was changed is AR Day property Management.**  
  

## See Also
[RecordRef Data Type](recordref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)