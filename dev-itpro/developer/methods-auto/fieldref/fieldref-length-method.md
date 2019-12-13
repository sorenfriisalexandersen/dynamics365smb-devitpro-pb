---
title: "Length Method"
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
# Length Method
Gets the maximum size of the field (the size specified in the DataLength property of the field). This method is usually used for finding the defined length of code and text fields.


## Syntax
```
Length :=   FieldRef.Length()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*FieldRef*  
&emsp;Type: [FieldRef](fieldref-data-type.md)  
An instance of the [FieldRef](fieldref-data-type.md) data type.  

## Return Value
*Length*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 For Text and Code fields this method returns the defined length. For other types of fields, it returns the fixed byte size, for example, Integer fields returns 4.  
  
## Example  
 The following example opens the Customer table as a RecordRef variable. The [FIELD Method \(RecordRef\)](../../methods-auto/recordref/recordref-field-method.md) creates a FieldRef for any specified field and stores the reference in the MyFieldRef variable. The LENGTH method retrieves the maximum size of the field and stores the value in the varLength variable. The value that is stored in the varLength is displayed in a message box. 

```
var
    MyFieldRef: FieldRef;
    CustomerRecref: RecordRef;
    varLength: Integer;
    varFieldNo: Integer;
    Text000: Label 'The maximum size of the field is %1.';
begin  
    varFieldNo := 1;  
    CustomerRecref.OPEN(DATABASE::Customer);  
    MyFieldRef := CustomerRecref.FIELD(varFieldNo);  
    varLength := MyFieldRef.LENGTH();  
    MESSAGE(Text000, varLength);  
end;
```  

## See Also
[FieldRef Data Type](fieldref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)