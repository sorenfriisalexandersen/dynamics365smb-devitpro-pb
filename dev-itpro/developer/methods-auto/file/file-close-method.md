---
title: "Close Method"
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
# Close Method
Closes a file that has been opened by the OPEN method (File).

> [!NOTE]
> This method is supported only in Business Central on-premises.

## Syntax
```
 File.Close()
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  

## Parameters
*File*  
&emsp;Type: [File](file-data-type.md)  
An instance of the [File](file-data-type.md) data type.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 If the file is not open, a run-time error will occur.  
  
## Example  
 The following example determines whether the specified file exists. If it exists, the [WRITEMODE Method \(File\)](../../methods-auto/file/file-writemode-method.md) allows the file to be open for writing. The [OPEN Method \(File\)](../../methods-auto/file/file-open-method.md) opens the file, the [WRITE Method \(File\)](../../methods/devenv-write-method-file.md) writes the text “Hello World” to the file, and then the CLOSE method closes the file. If the file does not exist, an error message is displayed. This example assumes that you have created the following file C:\\TestFolder\\TestFile2.txt.  

```
var
    FileName: Text;
    TestFile: File;
begin
    FileName := 'C:\TestFolder\TestFile2.txt';  
    if EXISTS(FileName) then begin  
      TestFile.WRITEMODE(TRUE);  
      TestFile.OPEN(FileName);  
      TestFile.WRITE('Hello World');  
      TestFile.CLOSE;  
    end else  
    MESSAGE('%1 does not exist.', FileName);  
end;
```  
  

## See Also
[File Data Type](file-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)