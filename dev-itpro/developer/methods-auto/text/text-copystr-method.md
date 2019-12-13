---
title: "CopyStr Method"
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
# CopyStr Method
Copies a substring of any length from a specific position in a string (text or code) to a new string.


## Syntax
```
NewString :=   Text.CopyStr(String: String, Position: Integer [, Length: Integer])
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*String*  
&emsp;Type: [String](../string/string-data-type.md)  
The string that you want to copy from.
        
*Position*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The position of the first character to copy. If the value of Position is less than 1, then the COPYSTR function returns an error. If Position is greater than the length of the string, then the COPYSTR function returns an empty string.
        
*Length*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The number of characters to copy. If the value of Length is less than 0, then the COPYSTR function returns an error. If the value of Length causes Position + Length to be > (total length of the string), then the result includes all the characters from Position to the end of the string. If you omit Length, then the resulting string includes all the characters from Position to the end of the string.  


## Return Value
*NewString*  
&emsp;Type: [String](../string/string-data-type.md)  
The copied string.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 If *Position* combined with *Length* exceeds the length of the string, all the characters from *Position* to the end of the string are returned.  
  
## Example  

```  
var
    Str: Text[30];
    Position: Integer;
    Length: Integer;
    NewStr: Text[30];
    Text000: Label 'Using the COPYSTR method';
    Text001: Label 'The original string is:>%1<';
    Text002: Label 'The copied string is:>%1<';
begin
    Str := Text000;  
    Position := 7;  
    Length := 8;  
    MESSAGE(Text001, Str);  
    NewStr := COPYSTR(Str, Position, Length);  
    MESSAGE(Text002, NewStr);  
end;
```  
  
 The first message window shows the original string:  
  
 **The original string is:**  
  
 **>Using the COPYSTR method\<**  
  
 The second message window shows the copied string:  
  
 **The copied string is:**  
  
 **>the COPY\<**  
  

## See Also
[Text Data Type](text-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)