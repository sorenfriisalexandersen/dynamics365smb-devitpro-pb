---
title: "An affix is required"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/10/2019
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
# AppSourceCop Rule AS0011
An affix is required  

## Description
An affix is required.

[//]: # (IMPORTANT: END>DO_NOT_EDIT)

In order to avoid name clashes for objects added by your extension and objects added by other extensions, an affix must be prepended or appended to the name of all new application objects, extension objects, and fields.

### Using the property mandatoryAffixes

The rule validates that at least one of the affixes specified in the `mandatoryAffixes` property of the `AppSourceCop.json` file is used either at prefix or at suffix on identifier names of new elements. 

|Setting|Mandatory|Value|
|-------|---------|-----|
|mandatoryAffixes|No|Affixes that must be prepended or appended to the name of all new application objects, extension objects, and fields.|

The `mandatoryAffixes` property expects to receive an array of string as follows:

```
{
    "mandatoryAffixes": [ "Foo", "Bar" ]
}
```

### Using the properties mandatoryPrefix and mandatorySuffix.

In order to preserve backward compatibility, the properties `mandatoryPrefix` and `mandatorySuffix` are still supported by the AppSourceCop.

Both properties expect to receive a string as follows:
```
{
    "mandatoryPrefix": "Prefix",
    "mandatorySuffix": "Suffix"
}
```

However, their meaning has been modified to be closer to the new `mandatoryAffixes` property. The mandatory prefix and mandatory suffix properties are now both defining an affix that can be used either as prefix or as suffix.

As a consequence, we encourage you to use the new property `mandatoryAffixes` that offers more flexibility by allowing you to define more than two affixes, but also a more meaningful name .

## See Also  
[AppSourceCop Analyzer](appsourcecop.md)  
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  