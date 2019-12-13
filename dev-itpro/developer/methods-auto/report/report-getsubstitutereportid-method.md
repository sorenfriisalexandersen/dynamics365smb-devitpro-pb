---
title: "GetSubstituteReportId Method"
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
# GetSubstituteReportId Method
Gets the ID of the report that will be run by the platform after considering any substitutions made by extensions.


## Syntax
```
NewReportId :=   Report.GetSubstituteReportId(ReportId: Integer)
```
## Parameters
*ReportId*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The ID of the report for which you want to retrieve the ID of the possible report substitute.  


## Return Value
*NewReportId*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The ID of the report that will be run by the platform after considering any substitutions made by extensions.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[Report Data Type](report-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)