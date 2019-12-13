---
title: "Get Method"
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
# Get Method
Gets a record based on the ID of the record.


## Syntax
```
[Ok := ]  RecordRef.Get(RecordID: RecordId)
```
## Parameters
*RecordRef*  
&emsp;Type: [RecordRef](recordref-data-type.md)  
An instance of the [RecordRef](recordref-data-type.md) data type.  

*RecordID*  
&emsp;Type: [RecordId](../recordid/recordid-data-type.md)  
The RecordID that contains the table number and the primary key of the table and is used to identify the record that you want to get.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the operation was successful; otherwise **false**.  If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method always uses the primary key for the table. It ignores any filters that are set, except security filters. Security filters are applied or ignored based on the Security Filter Mode. The current key and filters are not changed after you call this method. <!--Links For more information, see [Security Filter Modes](Security-Filter-Modes.md)-->.  
  
## Example  
 The following example opens the Customer table with the RecordRef variable, RecRef. The code assigns the first field in the table, which is the No. field, to MyFieldRef variable. The variable is assigned a value of 30000 by using the [FIELD Method \(RecordRef\)](recordref-field-method.md). The [RECORDID Method \(RecordRef\)](recordref-recordid-method.md) retrieves the record ID of the record that has a value of 30000 in the No. field. The GET method then uses the RecID variable then to retrieves the record.
 
```   
var
    RecRef: RecordRef;
    MyFieldRef: FieldRef;
    RecID: RecordId;
begin     
    RecRef.OPEN(DATABASE::Customer);  
    MyFieldRef := RecRef.FIELD(1);  
    MyFieldRef.VALUE := '30000';  
    if RecRef.FIND('=') then begin  
      RecID := RecRef.RECORDID;  
      RecRef.GET(RecID);  
    end;  
end;
```  

## See Also
[RecordRef Data Type](recordref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)