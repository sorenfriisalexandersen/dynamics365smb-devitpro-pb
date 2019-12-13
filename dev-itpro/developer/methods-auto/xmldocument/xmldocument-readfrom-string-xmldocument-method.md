---
title: "ReadFrom Method"
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
# ReadFrom Method
Reads and parses the XML document from the given data source.


## Syntax
```
[Ok := ]  XmlDocument.ReadFrom(Text: String, var Result: XmlDocument)
```
## Parameters
*Text*  
&emsp;Type: [String](../string/string-data-type.md)  
A string containing an XML document.
        
*Result*  
&emsp;Type: [XmlDocument](xmldocument-data-type.md)  
The XmlDocument parsed from the given data source.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the operation was successful; otherwise **false**.  If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[XmlDocument Data Type](xmldocument-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)