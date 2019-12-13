---
title: "InsStr Method"
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
# InsStr Method
Inserts a substring into a string.


## Syntax
```
NewString :=   Text.InsStr(String: String, SubString: String, Position: Integer)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*String*  
&emsp;Type: [String](../string/string-data-type.md)  
The string into which you want to insert a substring.
        
*SubString*  
&emsp;Type: [String](../string/string-data-type.md)  
The substring that you want to insert into String.
        
*Position*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
Specifies where to insert SubString. Position must be greater than or equal to 1. If Position is greater than the length of String, then the result is concatenated and copied to NewString.  


## Return Value
*NewString*  
&emsp;Type: [String](../string/string-data-type.md)  
The input string including the specified substring  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 If *SubString* is empty, then *String* is returned unchanged.  
  
 If *Position* is less than 1, an error is returned.  
  
 If *Position* is greater than the length of *String*, *SubString* is added at the end of *String*. For example, `INSSTR("Thomas","AAA",999)` returns 'ThomasAAA'.  
  
## Example   
```
var
    Str: Text[60];  
    SubString: Text[60];  
    NewString: Text[60]; 
    Text000: Label 'Press ENTER to continue.';  
    Text001: Label 'or ESC';
    Text002: Label ' The test string before INSSTR is called:>%1<';
    Text003: Label ' The resulting string after INSSTR is called:>%1<'; 
begin
    Str := Text000;  
    SubString := Text001;  
    MESSAGE(Text002, Str);  
    NewString := INSSTR(Str, SubString, 13);  
    MESSAGE(Text003, NewString);  
end;
```  
  
 The first message window displays the following:  
  
 **The test string before INSSTR is called:**  
  
 **>Press ENTER to continue.\<**  
  
 The second message window displays the following:  
  
 **The resulting string after INSSTR is called:**  
  
 **>Press ENTER or ESC to continue.\<**  

## See Also
[Text Data Type](text-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)