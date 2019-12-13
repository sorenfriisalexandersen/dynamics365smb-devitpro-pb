---
title: "DefaultLayout Method"
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
# DefaultLayout Method
Gets the default built-in layout type that is used on a specified report.


## Syntax
```
DefaultLayout :=   Report.DefaultLayout()
```

## Parameters
*Report*  
&emsp;Type: [Report](report-data-type.md)  
An instance of the [Report](report-data-type.md) data type.  

## Return Value
*DefaultLayout*  
&emsp;Type: [DefaultLayout](../defaultlayout/defaultlayout-option.md)  
The default built-in layout type that is used on a specified report.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 The default layout for a report is specified by the report's [DefaultLayout Property](../../properties/devenv-defaultlayout-property.md).

## See Also
[Report Data Type](report-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)