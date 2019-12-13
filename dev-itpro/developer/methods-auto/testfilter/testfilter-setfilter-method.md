---
title: "SetFilter Method"
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
# SetFilter Method
Applies a filter to the specified field on a test page.


## Syntax
```
 TestFilter.SetFilter(Field: TestFilterField, String: String)
```
## Parameters
*TestFilter*  
&emsp;Type: [TestFilter](testfilter-data-type.md)  
An instance of the [TestFilter](testfilter-data-type.md) data type.  

*Field*  
&emsp;Type: [TestFilterField](../testfilterfield/testfilterfield-data-type.md)  
The field that you want to apply the filter to.
          
*String*  
&emsp;Type: [String](../string/string-data-type.md)  
The filter to apply to the specified field.
          



[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[TestFilter Data Type](testfilter-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)