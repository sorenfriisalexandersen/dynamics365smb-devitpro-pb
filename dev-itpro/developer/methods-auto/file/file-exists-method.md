---
title: "Exists Method"
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
# Exists Method
Determines whether a file exists.

> [!NOTE]
> This method is supported only in Business Central on-premises.

## Syntax
```
[Ok := ]  File.Exists(Name: String)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*Name*  
&emsp;Type: [String](../string/string-data-type.md)  
The name of the file that you want to check. This includes the path. When you enter the path, consider these shortcuts:
-   You can omit the drive designation if the file is located on the current drive.
-   You can omit the full path if the file is located in the current directory.
-   You can enter only the subdirectory name if the file is located in a subdirectory of the current directory.
          


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the server instance has access to the file; otherwise **false**. If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
 The following example uses the EXISTS method to determine whether the specified file exists. If the file exists, then the [WRITEMODE Method \(File\)](../../methods-auto/file/file-writemode-method.md) allows the file to be open for writing. The [OPEN Method \(File\)](../../methods-auto/file/file-open-method.md) opens the file, the [WRITE Method \(File\)](../../methods/devenv-write-method-file.md) writes the text “Hello World” to the file, and then the [CLOSE Method \(File\)](../../methods-auto/file/file-close-method.md) method closes the file. If the file does not exist, an error message is displayed. This example assumes that you have created the following file C:\\TestFolder\\TestFile2.txt.  

```
 var
    TestFile: File;
    FileName: Text;
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