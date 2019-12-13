---
title: "Read Method"
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
# Read Method
Streams a BigText object that is stored as a BLOB in a table to a BigText variable.


## Syntax
```
[Ok := ]  BigText.Read(InStream: InStream)
```
## Parameters
*BigText*  
&emsp;Type: [BigText](bigtext-data-type.md)  
An instance of the [BigText](bigtext-data-type.md) data type.  

*InStream*  
&emsp;Type: [InStream](../instream/instream-data-type.md)  
The InStream object type that you use to stream a BLOB to a BigText variable.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the read transaction was successful, otherwise **false**.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 To delete the content in a BigText variable, use the [CLEAR Method](../../methods-auto/system/system-clear-joker-method.md).  
  
```  
CLEAR(BigText)  
```  
  
## Example  
 This example shows how to stream a BigText that is stored as a BLOB in a table to a BigText variable.  
  
```
var
    Bstr: BigText;
    Istream: InStream;
    EmployeeRec: Record Employee;
begin
    EmployeeRec.FIND('-');  
    EmployeeRec.CALCFIELDS(Picture);  
    EmployeeRec.Picture.CREATEINSTREAM(Istream);  
    Bstr.READ(Istream);  
end;
```  
  
 Use the [CALCFIELDS Method \(Record\)](../../methods-auto/record/record-calcfields-method.md) to calculate the BlobField. A BlobField is a binary large object \(maximum size 2 GB\) and must be calculated if you want to use it in AL or display it in the application.  

## See Also

[BigText Data Type](bigtext-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)