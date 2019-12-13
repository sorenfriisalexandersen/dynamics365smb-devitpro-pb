---
title: "GetRangeMin Method"
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
# GetRangeMin Method
Gets the minimum value in a range for a field.


## Syntax
```
Value :=   FieldRef.GetRangeMin()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*FieldRef*  
&emsp;Type: [FieldRef](fieldref-data-type.md)  
An instance of the [FieldRef](fieldref-data-type.md) data type.  

## Return Value
*Value*  
&emsp;Type: [Any](../any/any-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method is like the [GETRANGEMIN Method \(Record\)](../../methods-auto/record/record-getrangemin-method.md) method.  
  
## Example  
 The following example opens the Customer table as RecordRef variable, creates a FieldRef for the first field \(No.\) and stores the reference in the MyFieldRef variable. The [SETFILTER Method \(FieldRef\)](../../methods-auto/fieldref/fieldref-setfilter-method.md) sets a filter that selects records in the range 10000 to 40000 from the No. field. The GETRANGEMIN method retrieves and stores the minimum value that is set in the filter, stores the value in the varMin variable and displays it in a message box. The varMin variable contains 10000 which is the minimum value that is set in the filter. 
 
 ```
var
    MyFieldRef: FieldRef;
    CustomerRecref: RecordRef;
    varMin: Text;
    Text000: Label 'The minimum value in the filter is %1.';
begin
    CustomerRecref.OPEN(DATABASE::Customer);  
    MyFieldRef := CustomerRecref.FIELD(1);  
    MyFieldRef.SETFILTER('10000..40000');  
    varMin := MyFieldRef.GETRANGEMIN();  
    MESSAGE(Text000, varMin);  
end;
```  
  

## See Also
[FieldRef Data Type](fieldref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)