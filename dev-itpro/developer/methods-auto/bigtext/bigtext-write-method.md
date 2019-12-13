---
title: "Write Method"
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
# Write Method
Streams a BigText object to a BLOB field in a table.


## Syntax
```
[Ok := ]  BigText.Write(OutStream: OutStream)
```
## Parameters
*BigText*  
&emsp;Type: [BigText](bigtext-data-type.md)  
An instance of the [BigText](bigtext-data-type.md) data type.  

*OutStream*  
&emsp;Type: [OutStream](../outstream/outstream-data-type.md)  
The stream to which you write a BigText.
        


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the write transaction was successful, otherwise **false**.
        


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 To delete the content in a BigText variable, use the [CLEAR Method](../../methods-auto/system/system-clear-joker-method.md).  
  
```  
CLEAR(BigText)  
```  
  
## Example  
 This example shows how to stream a BigText to a BLOB field in a table.  

```
var
    Bstr: BigText;
    Ostream: OutStream;
    ItemRec: Record Item;
begin 
    Bstr.ADDTEXT('This is the text string that we want to store in a BLOB field.');  
    ItemRec.Picture.CREATEOUTSTREAM(Ostream);  
    Bstr.WRITE(Ostream);  
    ItemRec.INSERT;  
end;
```  

## See Also

[BigText Data Type](bigtext-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)