---
title: "CopyStream Method"
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
# CopyStream Method
Copies the information that is contained in an InStream to an OutStream.


## Syntax
```
[Ok := ]  System.CopyStream(OutStream: OutStream, InStream: InStream [, BytesToRead: Integer])
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*OutStream*  
&emsp;Type: [OutStream](../outstream/outstream-data-type.md)  
The OutStream object to which you will copy the information; the destination stream.
        
*InStream*  
&emsp;Type: [InStream](../instream/instream-data-type.md)  
The InStream object from which you want to copy; the source stream.
        
*BytesToRead*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the operation was successful; otherwise **false**.  If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  

```  
var
    F1: File;
    F2: File;
    InS: InStream;
    OutS: OutStream;
begin
    F1.OPEN('c:\Test.txt');  
    F1.CREATEINSTREAM(InS);  
    F2.CREATE('c:\CopyTest.txt');  
    F2.CREATEOUTSTREAM(OutS);  
    COPYSTREAM(OutS,InS);  
    F1.CLOSE();  
    F2.CLOSE();  
end;
```  


## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)