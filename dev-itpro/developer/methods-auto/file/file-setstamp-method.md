---
title: "SetStamp Method"
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
# SetStamp Method
Sets a timestamp for a file.

> [!NOTE]
> This method is supported only in Business Central on-premises.

## Syntax
```
[Ok := ]  File.SetStamp(Name: String, Date: Date [, Time: Time])
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*Name*  
&emsp;Type: [String](../string/string-data-type.md)  
The name of the file, including its path. When you enter the path, keep in mind these shortcuts:
-   You can omit the drive designation, if the file is located on the current drive.
-   You can omit the full path, if the file is located in the current directory.
-   You can enter only the subdirectory name, if the file is located in a subdirectory of the current directory.
      
*Date*  
&emsp;Type: [Date](../date/date-data-type.md)  
The date that you want stamped on the file.
        
*Time*  
&emsp;Type: [Time](../time/time-data-type.md)  
The time that you want stamped on the file.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the operation was successful; otherwise **false**.  If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
 The following example sets timestamp for that a file that is named varFileName. The date and time are set to the current date and on your computer respectively. The code example assumes that you have created the following file: 'C:\\MyFolder\\MyText.txt'. The following example requires that you create the following global variables and text constant.  

```
 var
    varFileName: Text;
    varDate: Date;
    varTime: Time;
    Text000: Label 'The timestamp for this file is Date: %1 Time: %2.';
begin
    VarFileName := 'C:\MyFolder\MyText.txt';  
    varDate := TODAY;  
    varTime := TIME;  
    SETSTAMP(VarFileName, varDate, varTime);  
    MESSAGE(Text000, varDate, varTime);  
end;
```  
  
## See Also
[File Data Type](file-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)