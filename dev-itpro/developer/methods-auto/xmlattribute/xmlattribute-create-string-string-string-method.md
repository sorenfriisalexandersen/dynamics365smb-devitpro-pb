---
title: "Create Method"
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
# Create Method
Creates an XmlAttribute node.


## Syntax
```
XmlAttribute :=   XmlAttribute.Create(LocalName: String, NamespaceUri: String, Value: String)
```
## Parameters
*LocalName*  
&emsp;Type: [String](../string/string-data-type.md)  
The local name of the attribute.
        
*NamespaceUri*  
&emsp;Type: [String](../string/string-data-type.md)  
The namespace URI of the attribute.
        
*Value*  
&emsp;Type: [String](../string/string-data-type.md)  
The value of the attribute.  


## Return Value
*XmlAttribute*  
&emsp;Type: [XmlAttribute](xmlattribute-data-type.md)  
The created XmlAttribute node.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[XmlAttribute Data Type](xmlattribute-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)