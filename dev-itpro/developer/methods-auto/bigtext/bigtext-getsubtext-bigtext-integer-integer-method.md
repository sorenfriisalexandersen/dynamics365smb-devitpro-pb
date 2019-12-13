---
title: "GetSubText Method"
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
# GetSubText Method
Gets part of a BigText variable.


## Syntax
```
[Length := ]  BigText.GetSubText(var Variable: BigText, Position: Integer [, Length: Integer])
```
## Parameters
*BigText*  
&emsp;Type: [BigText](bigtext-data-type.md)  
An instance of the [BigText](bigtext-data-type.md) data type.  

*Variable*  
&emsp;Type: [BigText](bigtext-data-type.md)  
The sub text of the BigText that is retrieved. This is the actual text that is returned.
        
*Position*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The position in the BigText variable that the sub text is to be retrieved from. If this parameter is less than one, then a run-time error occurs. If this parameter is greater than the length of the BigText variable, then an empty string is returned. If the value of this parameter plus the value of the Length parameter is greater than the length of the BigText variable, then the remainder of the BigText variable from the position specified by this parameter is returned.
        
*Length*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The length of the sub text that should be retrieved. This parameter is optional. If this parameter is omitted the method retrieves a sub text that starts at Position and runs to the end of the BigText variable. If this parameter is less than 0, then a run-time error occurs. If the value of the Position parameter plus the value of this parameter is greater than the length of the BigText variable, then the remainder of the BigText variable from the position specified by this parameter is returned.
        


## Return Value
*Length*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The length of the result text.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)


## Remarks  
 The first character in a BigText variable is position 1.  
  
 To delete the content in a BigText variable use the [CLEAR Method](../../methods-auto/system/system-clear-joker-method.md). The following code snippet shows the syntax for the clear method. `CLEAR(BigText)`.  
  
## Example  
 The following examples demonstrate how to use the GETSUBTEXT method. This example requires that you create the following global variables and text constant.  
  
```
var
    MyBigText: BigText;
    VarSubText: Text;
    Text000: Label 'VarSubText = %1';
```
  
 The following example initializes the content of the MyBigText variable with the text `ABCDEFG`. The method starts from the third position \(the character C\) in the MyBigText variable and retrieves two characters. The result is the subtext CD. This is because the number 2 is specified for *Length* .  
  
```  
  
MyBigText.ADDTEXT('ABCDEFG');  
MyBigText.GETSUBTEXT(VarSubText, 3, 2); // Returns CD.  
MESSAGE(Text000, VarSubText);  
```  
  
## Example  
 The following example initializes the content of the MyBigText variable with the text `ABCDEFG`. The method returns an error because zero is specified for *Position*.  
  
```  
  
MyBigText.ADDTEXT('ABCDEFG');  
MyBigText.GETSUBTEXT(VarSubText, 0, 4); // Returns an error.  
MESSAGE(Text000, VarSubText);  
  
```  
  
## Example  
 The following example initializes the content of the MyBigText variable with the text `ABCDEFG`. The method returns an error because a negative number is specified for *Length*.  
  
```  
  
MyBigText.ADDTEXT('ABCDEFG');  
MyBigText.GETSUBTEXT(VarSubText, 5, -2); // Returns an error.  
MESSAGE(Text000, VarSubText);  
```  
  
## Example  
 The following example initializes the content of the MyBigText variable with the text `ABCDEFG`. The method returns an empty string because the number specified for *position* is greater than the length of the MyBigText variable.  
  
```  
  
MyBigText.ADDTEXT('ABCDEFG');  
MyBigText.GETSUBTEXT(VarSubText, 15, 4); // Returns an empty string.  
MESSAGE(Text000, VarSubText);  
  
```  
  
## Example  
 The following example initializes the content of the MyBigText variable with the text `ABCDEFG`. The method starts from the forth position \(the character D\) and retrieves all the characters in the MyBigText string. The result is the subtext DEFG. This is because the number specified for *Length* is greater than the length of the MyBigText variable.  
  
```  
  
MyBigText.ADDTEXT('ABCDEFG');  
MyBigText.GETSUBTEXT(VarSubText, 4, 15); // Returns DEFG.  
MESSAGE(Text000, VarSubText);  
  
```  

## See Also

[BigText Data Type](bigtext-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)