---
title: "IsText Method"
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
# IsText Method
Indicates whether an AL variant contains a Text variable.


## Syntax
```
Ok :=   Variant.IsText()
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
**true** if the AL variant contains a Text variable, otherwise **false**.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
 The following example determines whether an AL variant contains a text variable. The code initializes the MyText variable with a text value. The MyText variable is assigned to the variant variable that is named MyVariant. The **ISTEXT** method determines whether the variant contains a text variable and stores the return value in the varResult variable. In this case, the variant contains a text variable so **Yes** is returned and displayed in a message box. The **ISCODE** method determines whether the variant contains a code variable. The return value is **No** because the variant does not contain a code. 

```  
var
    MyText: Text[50];
    MyVariant: Variant;
    varResult: Boolean;
    Text000: Label 'Does the variant >%1< contain a text variable? %2.';
    Text001: Label 'Does the variant >%1< contain a code variable? %2.';
begin
    MyText := 'This is some text';  
    MyVariant :=  MyText;  
    varResult := MyVariant.ISTEXT;  
    MESSAGE(Text000,MyVariant,varResult);  
    varResult := MyVariant.ISCODE;  
    MESSAGE(Text001,MyVariant,varResult);  
end;
```  

## See Also
[Variant Data Type](variant-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)