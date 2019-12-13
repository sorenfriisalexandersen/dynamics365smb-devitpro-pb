---
title: "Count Method"
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
# Count Method
Counts the number of records that are in the filters that are currently applied to the table referred to by the RecordRef.


## Syntax
```
Number :=   RecordRef.Count()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*RecordRef*  
&emsp;Type: [RecordRef](recordref-data-type.md)  
An instance of the [RecordRef](recordref-data-type.md) data type.  

## Return Value
*Number*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The number of records in the table.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method returns the number of records that meet the conditions of any filters associated with the records. If no filters are set, the method shows the total number of records in the table.  
  
> [!NOTE]  
>  The COUNT method does not lock the table before it retrieves the number of records in the table. This means that the method reads both uncommitted and committed data, which could cause the number of records that is returned to be inaccurate. To make sure that the count is accurate, use the [LOCKTABLE Method \(RecordRef\)](recordref-locktable-method.md) before you use the COUNT method.  
  
 In previous versions of [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)], the COUNT method ignored security filters and always returned the total number of records unless you called the SETPERMISSIONFILTER method to get a filtered count. In [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)], the COUNT method adheres to the [SecurityFiltering Property](../../properties/devenv-securityfiltering-property.md). <!--Links For more information, see [Security Filter Modes](Security-Filter-Modes.md)-->.  
  
 This method works just like the [COUNT Method \(Record\)](../record/record-count-method.md).  
  
## Example  
 The following example opens table number 18 \(Customer\) as a RecordRef that is named MyRecordRef. The [LOCKTABLE Method \(RecordRef\)](recordref-locktable-method.md) locks the table. The COUNT method then retrieves the number of records in the table. The number of records is stored in the Count variable. The name of the table and the number of records in the table is displayed in a message box. The varTableNo variable can be used to open any table and get the number of records in that table by changing the value of the varTableNo variable.
 
```  
var
    MyRecordRef: RecordRef;
    varTableNo: Integer;
    Count: Integer;
    Text000: Label 'The number of records in the %1 table is: %2.';
begin
    varTableNo := 18;  
    MyRecordRef.OPEN(varTableNo);  
    MyRecordRef.LOCKTABLE;  
    Count := MyRecordRef.COUNT;  
    MESSAGE(Text000, MyRecordRef.NAME, Count);  
end;
```  
  

## See Also
[RecordRef Data Type](recordref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)