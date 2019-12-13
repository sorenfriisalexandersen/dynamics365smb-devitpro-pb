---
title: "XmlNamespaceManager Data Type"
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
# XmlNamespaceManager Data Type
Represents a namespace manager that can be used to resolve, add and remove namespaces to a collection. It also provides scope management for these namespaces.



The following methods are available on instances of the XmlNamespaceManager data type.

|Method name|Description|
|-----------|-----------|
|[NameTable([XmlNameTable])](xmlnamespacemanager-nametable-method.md)|Gets or sets the XmlNameTable associated with this object.|
|[AddNamespace(String, String)](xmlnamespacemanager-addnamespace-method.md)|Adds the given namespace to the collection.|
|[HasNamespace(String)](xmlnamespacemanager-hasnamespace-method.md)|Gets a value indicating whether the supplied prefix has a namespace defined for the current scope.|
|[LookupNamespace(String, var Text)](xmlnamespacemanager-lookupnamespace-method.md)|Gets the namespace URI for the specified prefix.|
|[LookupPrefix(String, var Text)](xmlnamespacemanager-lookupprefix-method.md)|Finds the prefix declared for the given namespace URI.|
|[RemoveNamespace(String, String)](xmlnamespacemanager-removenamespace-method.md)|Removes the given namespace for the given prefix.|
|[PushScope()](xmlnamespacemanager-pushscope-method.md)|Pushes a namespace scope onto the stack.|
|[PopScope()](xmlnamespacemanager-popscope-method.md)|Pops a namespace scope off the stack.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  