---
title: "ObjectId Method"
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
# ObjectId Method
Gets or sets the name or number of the report.


## Syntax
```
String :=   Report.ObjectId([UseNames: Boolean])
```
## Parameters
*Report*  
&emsp;Type: [Report](report-data-type.md)  
An instance of the [Report](report-data-type.md) data type.  

*UseNames*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** (default value) if the returned string contains the name of the report, **false** if the returned string contains the number of the report.  


## Return Value
*String*  
&emsp;Type: [String](../string/string-data-type.md)  
The name or number of the report.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Report Data Type](report-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)