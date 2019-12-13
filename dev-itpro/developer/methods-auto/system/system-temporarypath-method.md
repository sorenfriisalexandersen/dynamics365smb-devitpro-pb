---
title: "TemporaryPath Method"
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
# TemporaryPath Method
Gets the path of the directory where the temporary file is stored.

> [!NOTE]
> This method is supported only in Business Central on-premises.

## Syntax
```
String :=   System.TemporaryPath()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
> [!NOTE]  
> This method can be invoked without specifying the data type name.  


## Return Value
*String*  
&emsp;Type: [String](../string/string-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method returns a string that contains the path of the directory where the temporary file for [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)] is stored. This string ends with a backslash \('\\'\) and does not contain the name of the temp file.  
  
 The string cannot contain more than 255 characters.  
  
 If this method is called from an application that is running on a [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)] Application Server, it returns the path of the directory where the [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)] Application Server is installed. 

## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)