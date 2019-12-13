---
title: "Number Method"
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
# Number Method
Gets the table ID (number) of the table that contains the record that was referred to by the RecordRef.


## Syntax
```
No :=   RecordRef.Number()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*RecordRef*  
&emsp;Type: [RecordRef](recordref-data-type.md)  
An instance of the [RecordRef](recordref-data-type.md) data type.  

## Return Value
*No*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The table ID of the table that contains the record that was referred to by the RecordRef.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 In versions of [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)] earlier than [!INCLUDE[nav7long](../../includes/nav7long_md.md)], if a RecordRef referred to a temporary table, then the table number value of the RecordRef was the run-time generated sequence ID, which is from the base value of 2000100000. You could use the table number to determine whether a RecordRef referred to a temporary table. In [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)], the table number value of a RecordRef always contains the ID of the originating physical table and not the run-time generated sequence ID. If you previously used the NUMBER Method \(RECORDREF\) to test for the sequence number and determine whether the RecordRef was temporary, then you must use the [ISTEMPORARY Method \(RecordRef\)](recordref-istemporary-method.md) in [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)] instead.  
  
## Example  
 The following example opens the Customer table \(18\) as a RecordRef object. The [OPEN Method \(RecordRef\)](recordref-open-method.md) accepts `DATABASE::Customer` as an integer. The NUMBER method retrieves the table number and displays the name and number of the table in a message box. 
  
```  
var
    MyRecordRef: RecordRef;
    varDatabaseName: Integer;
    varTableNumber: Integer;
    Text000: Label '%1 is table %2.'; 
begin   
    varDatabaseName := DATABASE::Customer;  
    MyRecordRef.OPEN(varDatabaseName);  
    varTableNumber := MyRecordRef.NUMBER;  
    MESSAGE(Text000, MyRecordRef.CAPTION, varTableNumber);  
end;
  
```  
  

## See Also
[RecordRef Data Type](recordref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)