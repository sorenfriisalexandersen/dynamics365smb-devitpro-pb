---
title: "GetBySystemId Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/14/2019
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
# GetBySystemId Method
Gets a record by its SystemId.


## Syntax
```
[RecordExists := ]  Record.GetBySystemId(SystemId: Guid)
```
## Parameters
*Record*  
&emsp;Type: [Record](record-data-type.md)  
An instance of the [Record](record-data-type.md) data type.  

*SystemId*  
&emsp;Type: [Guid](../guid/guid-data-type.md)  
The SystemId of the record to retrieve.  


## Return Value
*RecordExists*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the record exists; otherwise **false**.If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## Remarks

Every record has a SystemId, which is stored in the SystemId field of the table. The SystemId cannot be changed.

## Example
  
This example shows how to use the GETBYSYSTEMID method to retrieve a record.

```
var
    CustomerRec: Record Customer;
    Text000: Label 'Customer was found.';
begin
    If CustomerRec.GetBySystemId('{5286305A-08A3-E911-8180-001DD8B7338E}') then
    Message(Text000);
end;
```
## See Also

[SystemId Field](../../devenv-table-object.md#systemid)  
[Record Data Type](record-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  