---
title: "IsTextConstant Method"
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
# IsTextConstant Method
Indicates whether an AL variant contains a Text constant.


## Syntax
```
Ok :=   Variant.IsTextConstant()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*Variant*  
&emsp;Type: [Variant](variant-data-type.md)  
An instance of the [Variant](variant-data-type.md) data type.  

## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the AL variant contains a Text constant, otherwise **false**.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
 The following example determines whether an AL variant contains a text constant. The code assigns the Text000 text constant to the variant variable that is named MyVariant. The **ISTEXTCONSTANT** method determines whether the variant contains a text constant and stores the return value in the varResult variable. In this case, the variant contains a text constant so **Yes** is returned and displayed in a message box. 
 
```  
var
    MyVariant: Variant;
    varResult: Boolean;
    Text000: Label 'This is some text.";
    Text001: Label 'DOes the variant contain a text constant? %1.';
begin
    MyVariant := Text000;  
    varResult := MyVariant.ISTEXTCONSTANT;  
    MESSAGE(Text001,MyVariant,varResult);  
    MESSAGE(Text001,varResult);  
end;
```  

## See Also
[Variant Data Type](variant-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)