---
title: "TestField Method"
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
# TestField Method
Determines whether the contents of a field matches a given value. If the contents differ from the given value, an error message is displayed.


## Syntax
```
 FieldRef.TestField()
```

## Parameters
*FieldRef*  
&emsp;Type: [FieldRef](fieldref-data-type.md)  
An instance of the [FieldRef](fieldref-data-type.md) data type.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method is like the [TESTFIELD Method \(Record\)](../../methods-auto/record/record-testfield-joker-method.md) method.  
  
## Example  
 The following example opens the Customer table as a RecordRef variable that is named CustomerRecref, created a reference to the first field \(No\) and stores the reference in the MyFieldRef variable. The [VALUE Method \(FieldRef, TestPage Field\)](../../methods/devenv-value-method-fieldref-testpage-field.md) sets the No. field to a blank text. The TESTFIELD method determines whether the contents of the field match 10000, the specified value. In this case, the content does not match so the [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)] throws an exception. If the there is a match, no exception is thrown.  

 ```
var
    MyFieldRef: FieldRef;
    CustomerRecref: RecordRef;
begin
    CustomerRecref.OPEN(DATABASE::Customer);  
    MyFieldRef := CustomerRecref.FIELD(1);  
    MyFieldRef.VALUE := '';  
    MyFieldRef.TESTFIELD('10000');  
end;
```  
  
 In this example, the [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)] displays following error message:  
  
 No. must be equal to 10000 in Customer: No.=. Current value is ‘’.  
  
## Example  
 If the value of the No. field is set to a value other than 10000, [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)] displays the following error message:  
  
 No. must be equal to 10000 in Customer: No.=AAA10000. Current value is ‘AAA10000’.  
  
```  
  
CustomerRecref.OPEN(DATABASE::Customer);  
MyFieldRef := CustomerRecref.FIELD(1);  
MyFieldRef.VALUE := 'AAA 10000';  
MyFieldRef.TESTFIELD('10000');  
```  

## See Also
[FieldRef Data Type](fieldref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)