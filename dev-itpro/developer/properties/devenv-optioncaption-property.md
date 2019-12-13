---
title: "OptionCaption Property"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: SusanneWindfeldPedersen
---

# OptionCaption Property
Sets the text string options that are displayed to the user.  
  
## Applies To  
  
- Pages  
  
- Reports  
  
- Variables  
  
## Syntax
```
field(1300; "Payment Prediction"; Option)
{
    OptionMembers = " ",Late,"On-Time";
    OptionCaption = ' ,Late,On-Time';
}
```
```
field(1301; "Prediction Confidence"; Option)
{
    OptionMembers = " ",Low,Medium,High;
    OptionCaption = ' ,Low,Medium,High';
}
```

## Remarks  
**OptionCaption** sets the text used to show the option values available for a variable or a field on a page or report. The [OptionString Property](devenv-optionstring-property.md) contains the set of values that are acceptable choices. If you have set the [OptionCaptionML Property](devenv-optioncaptionml-property.md), this overrides the OptionCaption setting.  
  
## See Also  
 [OptionString Property](devenv-optionstring-property.md)   
 [OptionCaptionML Property](devenv-optioncaptionml-property.md)