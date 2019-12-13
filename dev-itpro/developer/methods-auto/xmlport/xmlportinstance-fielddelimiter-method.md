---
title: "FieldDelimiter Method"
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
# FieldDelimiter Method
Gets and sets the FiledDelimiter used when running, importing or exporting the XmlPort.


## Syntax
```
[Delimiter := ]  Xmlport.FieldDelimiter([Delimiter: String])
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
## Parameters
*Xmlport*  
&emsp;Type: [Xmlport](xmlport-data-type.md)  
An instance of the [Xmlport](xmlport-data-type.md) data type.  

*Delimiter*  
&emsp;Type: [String](../string/string-data-type.md)  
The new value of the FieldDelimiter.  


## Return Value
*Delimiter*  
&emsp;Type: [String](../string/string-data-type.md)  
The FieldDelimiter used when running, importing or exporting the XmlPort.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Xmlport Data Type](xmlport-data-type.md)  
[FieldDelimiter Property](../../properties/devenv-fielddelimiter-property.md)   
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)