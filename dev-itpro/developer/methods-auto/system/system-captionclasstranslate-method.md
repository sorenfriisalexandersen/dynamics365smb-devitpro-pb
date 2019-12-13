---
title: "CaptionClassTranslate Method"
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
# CaptionClassTranslate Method
Returns a translated version of the caption string. The string is translated to the current local language.


## Syntax
```
String :=   System.CaptionClassTranslate(CaptionClassText: String)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*CaptionClassText*  
&emsp;Type: [String](../string/string-data-type.md)  
A literal string that defines the caption.  


## Return Value
*String*  
&emsp;Type: [String](../string/string-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 You can use the [SELECTLATESTVERSION Method \(Database\)](../../methods-auto/database/database-selectlatestversion-method.md) to clear the current session's cache for the CaptionClassTranslate strings. The strings will then be reevaluated by the **CaptionClassTranslate** method trigger \(ID 15\) in codeunit 1.  


## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)