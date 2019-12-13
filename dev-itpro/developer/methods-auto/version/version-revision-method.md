---
title: "Revision Method"
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
# Revision Method
Gets the revision number from the version.


## Syntax
```
RevisionVersion :=   Version.Revision()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*Version*  
&emsp;Type: [Version](version-data-type.md)  
An instance of the [Version](version-data-type.md) data type.  

## Return Value
*RevisionVersion*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The revision version number of the version.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Version Data Type](version-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)