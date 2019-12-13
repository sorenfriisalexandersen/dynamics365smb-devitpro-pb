---
title: "FindFirst Method"
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
# FindFirst Method
Finds the first record in a table based on the current key and filter.


## Syntax
```
[Ok := ]  RecordRef.FindFirst()
```

## Parameters
*RecordRef*  
&emsp;Type: [RecordRef](recordref-data-type.md)  
An instance of the [RecordRef](recordref-data-type.md) data type.  

## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the operation was successful; otherwise **false**.  If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 You should use this method instead of FIND\('-'\) when you need only the first record.  
  
 You should use this method only when you explicitly want to find the first record in a table or set. Do not use this method in combination with repeat..until.  
  
## Example  
 The following example opens the Item table \(27\) as a RecordRef variable that is named ItemRecref. The FINDFIRST method searches for the first record in the table. If the record is found, the description and unit price of the item in the record are displayed in a message box. Otherwise, a message that indicates that the first item was not found is displayed. 
 
```  
var
    ItemRecref: RecordRef;
    Text000: Label 'The first item is %1 and the unit price is %2.';
    Text001: Label 'The first item was not found.';
begin 
    ItemRecref.OPEN(27);  
    if ItemRecref.FINDFIRST then  
      MESSAGE(Text000, ItemRecref.FIELD(3),  ItemRecref.FIELD(18))  
    else  
      MESSAGE(Text001);  
end;
  
```  

## See Also
[RecordRef Data Type](recordref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)