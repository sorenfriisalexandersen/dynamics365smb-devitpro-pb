---
title: "Last Method"
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
# Last Method
Sets the current row of the test page as the last row in the data set.


## Syntax
```
[Ok := ]  TestRequestPage.Last()
```

## Parameters
*TestRequestPage*  
&emsp;Type: [TestRequestPage](testrequestpage-data-type.md)  
An instance of the [TestRequestPage](testrequestpage-data-type.md) data type.  

## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if a last row is present, otherwise **false**. Throws a NavTestPageNotOpenedException if the page is not opened.
        


[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also
[TestRequestPage Data Type](testrequestpage-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)