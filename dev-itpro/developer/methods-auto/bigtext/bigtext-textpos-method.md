---
title: "TextPos Method"
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
# TextPos Method
Gets the position at which a specific string first occurs in this BigText instance.


## Syntax
```
Position :=   BigText.TextPos(String: String)
```
## Parameters
*BigText*  
&emsp;Type: [BigText](bigtext-data-type.md)  
An instance of the [BigText](bigtext-data-type.md) data type.  

*String*  
&emsp;Type: [String](../string/string-data-type.md)  
The text string to search for in the BigText variable. If this parameter is empty, then 0 is returned.
        


## Return Value
*Position*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The position at which a specific string first occurs in this BigText instance.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 The first character in a *BigText* variable is position 1.  
  
## Example  
 The following examples show how to use the [TEXTPOS Method](../../methods-auto/bigtext/bigtext-textpos-method.md). These examples require that you create the following global variables and text constant.  

```
var
    MyBigText: BigText;
    VarPosition: Text;
    Text000: Label 'VarPosition = %1';
```
  
 The following examples first initialize the content of the *BigText* variable with the text `ABCDEFG`.  
  
 In this example, the first occurrence of the character B \(the first character of the specified text\) is found in the second position in the MyBigText variable so the method returns 2. The return value is stored in the variable VarPosition and displayed in a message box.  
  
```  
MyBigText.ADDTEXT('ABCDEFG');  
VarPosition := MyBigText.TEXTPOS('BCD'); // Returns 2.  
MESSAGE(Text000, VarPosition);  
  
```  
  
## Example  
 In the following example, the method returns 0 because the specified string is not found in the MyBigText variable. The return value is stored in the variable VarPosition and displayed in a message box.  
  
```  
MyBigText.ADDTEXT('ABCDEFG');  
VarPosition := MyBigText.TEXTPOS(''); // Returns 0.  
MESSAGE(Text000, VarPosition);  
```  
  
## Example  
 In the following example, the method returns 0 because the specified string is not found in the MyBigText variable. The return value is stored in the variable VarPosition and displayed in a message box.  
  
```  
MyBigText.ADDTEXT('ABCDEFG');  
VarPosition := MyBigText.TEXTPOS('XYZ'); // Returns 0.  
MESSAGE(Text000, VarPosition);  
```  
  

## See Also

[BigText Data Type](bigtext-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)