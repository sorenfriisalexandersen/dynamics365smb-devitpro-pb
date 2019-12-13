---
title: "RequestFilterHeadingML Property"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: SusanneWindfeldPedersen
---

# RequestFilterHeadingML Property

Sets the text used as a heading for a request page tab. If this property is set, the heading set by the [RequestFilterHeading Property](devenv-requestfilterheading-property.md) is not used.

> [!NOTE]  
> To submit an app to AppSource, you must use .xliff translation files. For more information, see [Working with Translation Files](../devenv-work-with-translation-files.md).
  
## Applies To  
  
- Data items on reports
- Table elements on XMLports
  
## Example
```
RequestFilterHeadingML = DAN='Kundeliste'; // Customer list
```

## Remarks

**RequestFilterHeadingML** is multilanguage-enabled. This means that it can contain a list of text in different languages. The text that is used will be selected according to the current language setting of the user. The **RequestFilterHeadingML** property has the following format.  
  
<*Language ID*>=<*ReqFilterHeading*>  
  
<*Language ID*> is a Windows standard three-letter language ID and <*ReqFilterHeading*> is the caption text for this language. Semicolons separate entries.  

You can enter values for the **RequestFilterHeadingML** property in the following ways:  
  
- If you enter a **RequestFilterHeadingML**, this value will be inserted in **RequestFilterHeadingML** as the value for the language that is currently selected. If the language is set to Danish when a value is entered in **RequestFilterHeadingML**, **RequestFilterHeadingML** will be updated with a DAN=<*value*> string. You have to use the abbreviated name (DAN for Danish, for example) of the languages.  
  
## See Also  
[Request Pages](../devenv-request-pages.md)  
[Multilanguage Development](../devenv-multilanguage-development.md)