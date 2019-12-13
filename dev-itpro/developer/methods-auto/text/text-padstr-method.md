---
title: "PadStr Method"
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
# PadStr Method
Changes the length of a string to a specified length. If the string is shorter than the specified length, length spaces are added at the end of the string to match the length. If the string is longer than the specified length, the string is truncated. If the specified length is less than 0, an exception is thrown.


## Syntax
```
NewString :=   Text.PadStr(String: String, Length: Integer [, FillCharacter: String])
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*String*  
&emsp;Type: [String](../string/string-data-type.md)  
The string that you want to increase or decrease.
        
*Length*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The new length of the output string. If Length is less than the length of String, then String is truncated. Otherwise String is expanded with filler characters. If Length is less than 0, then an error is returned.
        
*FillCharacter*  
&emsp;Type: [String](../string/string-data-type.md)  
This is a string of length 1. This character is used to fill empty spaces at the end of the output string. If not specified, spaces are used as default. If the length of FillCharacter is not 1, an error is returned.  


## Return Value
*NewString*  
&emsp;Type: [String](../string/string-data-type.md)  
A copy of the string with the expected length.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 If you omit *FillCharacter* and *String* is shorter than *Length*, then spaces are added at the end of *String* to match *Length*.  
  
 If you omit *FillCharacter* and *String* is longer than *Length*, then *String* is truncated.  
  
## Example  

```  
var
    Str1: Text[30];
    Str2: Text[30];
    Len1: Integer;
    Len2: Integer;
    Text000: Label '13 characters';
    Text001: Label 'Four';
    Text002: Label 'Before PADSTR is called:\\';
    Text003: Label '>%1< has the length %2\\';
    Text004: Label '>%3< has the length %4\\';  
    Text005: Label 'After PADSTR is called:\\';    
begin
    Str1 := Text000;  
    Str2 := Text001;  
    Len1 := STRLEN(Str1);  
    Len2 := STRLEN(Str2);  
    MESSAGE(Text002 + Text003 + Text004, Str1, Len1, Str2, Len2);  
    Str1 := PADSTR(Str1, 5); // Truncate the length to 5  
    Str2 := PADSTR(Str2, 15, 'w'); // Concatenate w until length = 15  
    Len1 := STRLEN(Str1);  
    Len2 := STRLEN(Str2);  
    MESSAGE(Text005 + Text003 + Text004, Str1, Len1, Str2, Len2);  
end;
```  
  
 The first message window displays the following:  
  
 **Before PADSTR is called:**  
  
 **>13 characters\< has the length 13**  
  
 **>Four\< has the length 4**  
  
 The second message window displays the following:  
  
 **After PADSTR is called:**  
  
 **>13 ch\< has the length 5**  
  
 **>Fourwwwwwwwwwww\< has the length 15**  

## See Also
[Text Data Type](text-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)