---
title: "XmlCData Data Type"
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
# XmlCData Data Type
Represents a CData section.


The following methods are available on the XmlCData data type.


|Method name|Description|
|-----------|-----------|
|[Create(String)](xmlcdata-create-method.md)|Creates an XmlCData node.|

The following methods are available on instances of the XmlCData data type.

|Method name|Description|
|-----------|-----------|
|[Value([String])](xmlcdata-value-method.md)|Gets or sets the value of this node.|
|[AsXmlNode()](xmlcdata-asxmlnode-method.md)|Converts the node to an XmlNode.|
|[GetParent(var XmlElement)](xmlcdata-getparent-method.md)|Gets the parent XmlElement of this node.|
|[GetDocument(var XmlDocument)](xmlcdata-getdocument-method.md)|Gets the XmlDocument for this node.|
|[AddAfterSelf(Any,...)](xmlcdata-addafterself-method.md)|Adds the specified content immediately after this node.|
|[AddBeforeSelf(Any,...)](xmlcdata-addbeforeself-method.md)|Adds the specified content immediately before this node.|
|[ReplaceWith(Any,...)](xmlcdata-replacewith-method.md)|Replaces this node with the specified content.|
|[Remove()](xmlcdata-remove-method.md)|Removes this node from its parent element.|
|[WriteTo(OutStream)](xmlcdata-writeto-outstream-method.md)|Serializes and saves the current node to the given variable.|
|[WriteTo(XmlWriteOptions, OutStream)](xmlcdata-writeto-xmlwriteoptions-outstream-method.md)|Serializes and saves the current node to the given variable.|
|[WriteTo(var Text)](xmlcdata-writeto-text-method.md)|Serializes and saves the current node to the given variable.|
|[WriteTo(XmlWriteOptions, var Text)](xmlcdata-writeto-xmlwriteoptions-text-method.md)|Serializes and saves the current node to the given variable.|
|[SelectSingleNode(String, var XmlNode)](xmlcdata-selectsinglenode-string-xmlnode-method.md)|Selects the first XmlNode that matches the XPath expression.|
|[SelectSingleNode(String, XmlNamespaceManager, var XmlNode)](xmlcdata-selectsinglenode-string-xmlnamespacemanager-xmlnode-method.md)|Selects the first XmlNode that matches the XPath expression.|
|[SelectNodes(String, var XmlNodeList)](xmlcdata-selectnodes-string-xmlnodelist-method.md)|Selects a list of nodes matching the XPath expression.|
|[SelectNodes(String, XmlNamespaceManager, var XmlNodeList)](xmlcdata-selectnodes-string-xmlnamespacemanager-xmlnodelist-method.md)|Selects a list of nodes matching the XPath expression.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  