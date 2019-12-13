---
title: "RecordSeparator Method"
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
# RecordSeparator Method
Gets and sets the RecordSeparator used when running, importing or exporting the XmlPort.


## Syntax
```
[Separator := ]  Xmlport.RecordSeparator([Separator: String])
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
## Parameters
*Xmlport*  
&emsp;Type: [Xmlport](xmlport-data-type.md)  
An instance of the [Xmlport](xmlport-data-type.md) data type.  

*Separator*  
&emsp;Type: [String](../string/string-data-type.md)  
The new value of the RecordSeparator.  


## Return Value
*Separator*  
&emsp;Type: [String](../string/string-data-type.md)  
The RecordSeparator used when running, importing or exporting the XmlPort.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Xmlport Data Type](xmlport-data-type.md)  
[RecordSeparator Property](../../properties/devenv-recordseparator-property.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)