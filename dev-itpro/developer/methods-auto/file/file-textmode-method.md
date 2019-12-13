---
title: "TextMode Method"
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
# TextMode Method
Sets whether a file should be opened as an ASCII file or a binary file. Gets the current setting of this option for a file.

> [!NOTE]
> This method is supported only in Business Central on-premises.

## Syntax
```
[Textmode := ]  File.TextMode([Mode: Boolean])
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*File*  
&emsp;Type: [File](file-data-type.md)  
An instance of the [File](file-data-type.md) data type.  

*Mode*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
  


## Return Value
*Textmode*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method should be used before File.OPEN is used to open the file. If you use this method on a file that is already open, then an error occurs.  
  
## Example  
 The following example sets the TEXTMODE to **true** when the file is open for writing. This means the file contents will be written to a text file that is named 'C:\\TestFolder\\TestFile.txt' by using ASCII characters. The [WRITEMODE Method \(File\)](../../methods-auto/file/file-writemode-method.md) and the [OPEN Method \(File\)](../../methods-auto/file/file-open-method.md) open the file for writing and the text ‘Hello World’ is written. The [CLOSE Method \(File\)](../../methods-auto/file/file-close-method.md) closes the file after the file is written to. This example assumes that you have created a text file that is named C:\\TestFolder\\TestFile.txt.  
  
 ```
 var
    TestFile: File;
begin 
    TestFile.TEXTMODE(TRUE);  
    TestFile.WRITEMODE(TRUE);  
    TestFile.OPEN('C:\TestFolder\TestFile.txt');  
    TestFile.WRITE('Hello World');  
    TestFile.CLOSE;  
end;
```  
  

## See Also
[File Data Type](file-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)