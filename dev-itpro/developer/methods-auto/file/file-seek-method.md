---
title: "Seek Method"
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
# Seek Method
Sets a file pointer to a new position in an ASCII or binary file.

> [!NOTE]
> This method is supported only in Business Central on-premises.

## Syntax
```
 File.Seek(Position: Integer)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*File*  
&emsp;Type: [File](file-data-type.md)  
An instance of the [File](file-data-type.md) data type.  

*Position*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The position at which to set the pointer.  



[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method is often used with [POS Method \(File\)](../../methods-auto/file/file-pos-method.md) and [LEN Method \(File\)](../../methods-auto/file/file-len-method.md).  
  
## Example  
 The following example sets a pointer at position 20 in a file and truncates the file at the pointer position. The [WRITEMODE Method \(File\)](../../methods-auto/file/file-writemode-method.md) enables a file named C:\\TestFolder\\TestFile.txt to open in write mode. The SEEK method sets a pointer at position 20 in the file and then the [TRUNC Method \(File\)](../../methods-auto/file/file-trunc-method.md) truncates the contents of the file at the pointer position. This example assumes that you have created the text file C:\\TestFolder\\TestFile.txt.

```
 var
    TestFile: File;
begin
    TestFile.WRITEMODE(TRUE);  
    TestFile.OPEN('C:\TestFolder\TestFile.txt');  
    TestFile.SEEK(20);  
    TestFile.TRUNC;  
end;
  
```  
  

## See Also
[File Data Type](file-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)