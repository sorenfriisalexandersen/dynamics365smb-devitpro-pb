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
Creates a version object from the major, minor, build and revision numbers provided.


## Syntax
```
Value :=   Version.Create(Major: Integer, Minor: Integer [, Build: Integer] [, Revision: Integer])
```
## Parameters
*Major*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The major version number.
        
*Minor*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The minor version number.
        
*Build*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The build version number.
        
*Revision*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The revision version number.  


## Return Value
*Value*  
&emsp;Type: [Version](version-data-type.md)  
The version created from the provided major, minor, build and revision numbers.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Version Data Type](version-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)