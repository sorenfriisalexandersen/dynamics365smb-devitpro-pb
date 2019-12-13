---
title: "EOS Method"
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
# EOS Method
Indicates whether an input stream has reached End of Stream (EOS).


## Syntax
```
IsEOS :=   InStream.EOS()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*InStream*  
&emsp;Type: [InStream](instream-data-type.md)  
An instance of the [InStream](instream-data-type.md) data type.  

## Return Value
*IsEOS*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the stream has reached End of Stream; otherwise **false**.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 If you are reading data from an external component, EOS can return **FALSE** even though no more data is available. This may occur if you have not called READ first.  
  
## Example  
 The following example opens the text file in a folder that is named MyFolder. The data in the text file is read into and input stream variable named StreamInTest. The [InStream.EOS Method](../../methods/devenv-instream.eos-method.md) is used to determine whether the input stream has reached the end. If the stream has not reached the end, the stream is read into a text buffer, which indicates that the stream has not reached the end until the stream reaches the end. You must also create the following file 'c:\\MyFolder\\MyText.txt'.  

```
 var
    StreamInTest: InStream;
    FileTest: File;
    Buffer: Text;
begin
    FileTest.OPEN('c:\MyFolder\MyText.txt');  
    FileTest.CREATEINSTREAM(StreamInTest);  
    while not StreamInTest.EOS do begin 
      StreamInTest.READTEXT(Buffer);  
      //Do some processing  
      MESSAGE('Stream is still processing')  
    end;  
    MESSAGE('End of Stream');  
end;
```  
  

## See Also
[InStream Data Type](instream-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)