---
title: "XmlDocumentType Data Type"
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
# XmlDocumentType Data Type
Represents an XML document type.


The following methods are available on the XmlDocumentType data type.


|Method name|Description|
|-----------|-----------|
|[Create(String)](xmldocumenttype-create-string-method.md)|Creates an XmlDocumentType node.|
|[Create(String, String)](xmldocumenttype-create-string-string-method.md)|Creates an XmlDocumentType node.|
|[Create(String, String, String)](xmldocumenttype-create-string-string-string-method.md)|Creates an XmlDocumentType node.|
|[Create(String, String, String, String)](xmldocumenttype-create-string-string-string-string-method.md)|Creates an XmlDocumentType node.|

The following methods are available on instances of the XmlDocumentType data type.

|Method name|Description|
|-----------|-----------|
|[GetName(var Text)](xmldocumenttype-getname-method.md)|Gets the name for this Document Type Definition (DTD).|
|[SetName(String)](xmldocumenttype-setname-method.md)|Sets the name for this Document Type Definition (DTD).|
|[GetSystemId(var Text)](xmldocumenttype-getsystemid-method.md)|Gets the system identifier for this Document Type Definition (DTD).|
|[SetSystemId(String)](xmldocumenttype-setsystemid-method.md)|Sets the system identifier for this Document Type Definition (DTD).|
|[GetInternalSubset(var Text)](xmldocumenttype-getinternalsubset-method.md)|Gets the internal subset for this Document Type Definition (DTD).|
|[SetInternalSubset(String)](xmldocumenttype-setinternalsubset-method.md)|Sets the internal subset for this Document Type Definition (DTD).|
|[GetPublicId(var Text)](xmldocumenttype-getpublicid-method.md)|Gets the public identifier for this Document Type Definition (DTD).|
|[SetPublicId(String)](xmldocumenttype-setpublicid-method.md)|Sets the public identifier for this Document Type Definition (DTD).|
|[AsXmlNode()](xmldocumenttype-asxmlnode-method.md)|Converts the node to an XmlNode.|
|[GetParent(var XmlElement)](xmldocumenttype-getparent-method.md)|Gets the parent XmlElement of this node.|
|[GetDocument(var XmlDocument)](xmldocumenttype-getdocument-method.md)|Gets the XmlDocument for this node.|
|[AddAfterSelf(Any,...)](xmldocumenttype-addafterself-method.md)|Adds the specified content immediately after this node.|
|[AddBeforeSelf(Any,...)](xmldocumenttype-addbeforeself-method.md)|Adds the specified content immediately before this node.|
|[ReplaceWith(Any,...)](xmldocumenttype-replacewith-method.md)|Replaces this node with the specified content.|
|[Remove()](xmldocumenttype-remove-method.md)|Removes this node from its parent element.|
|[WriteTo(OutStream)](xmldocumenttype-writeto-outstream-method.md)|Serializes and saves the current node to the given variable.|
|[WriteTo(XmlWriteOptions, OutStream)](xmldocumenttype-writeto-xmlwriteoptions-outstream-method.md)|Serializes and saves the current node to the given variable.|
|[WriteTo(var Text)](xmldocumenttype-writeto-text-method.md)|Serializes and saves the current node to the given variable.|
|[WriteTo(XmlWriteOptions, var Text)](xmldocumenttype-writeto-xmlwriteoptions-text-method.md)|Serializes and saves the current node to the given variable.|
|[SelectSingleNode(String, var XmlNode)](xmldocumenttype-selectsinglenode-string-xmlnode-method.md)|Selects the first XmlNode that matches the XPath expression.|
|[SelectSingleNode(String, XmlNamespaceManager, var XmlNode)](xmldocumenttype-selectsinglenode-string-xmlnamespacemanager-xmlnode-method.md)|Selects the first XmlNode that matches the XPath expression.|
|[SelectNodes(String, var XmlNodeList)](xmldocumenttype-selectnodes-string-xmlnodelist-method.md)|Selects a list of nodes matching the XPath expression.|
|[SelectNodes(String, XmlNamespaceManager, var XmlNodeList)](xmldocumenttype-selectnodes-string-xmlnamespacemanager-xmlnodelist-method.md)|Selects a list of nodes matching the XPath expression.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  