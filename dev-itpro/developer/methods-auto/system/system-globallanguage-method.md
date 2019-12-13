---
title: "GlobalLanguage Method"
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
# GlobalLanguage Method
Gets and sets the current global language setting.


## Syntax
```
[LanguageID := ]  System.GlobalLanguage([NewLanguageID: Integer])
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*NewLanguageID*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The Microsoft language ID (LCID), such as 1033 for English (US).
        


## Return Value
*LanguageID*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The Microsoft language ID (LCID).
        


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 The LanguageID is a standard Windows language ID. The Windows Language virtual table contains a list of these IDs and the corresponding names and short names.  
  
 For more information, see [Multilanguage Development](../../devenv-multilanguage-development.md). 
 
## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)