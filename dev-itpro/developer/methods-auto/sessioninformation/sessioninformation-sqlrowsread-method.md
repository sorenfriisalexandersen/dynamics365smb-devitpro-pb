---
title: "SqlRowsRead Method"
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
# SqlRowsRead Method
Gets the amount of SQL rows read on the session, since the session started.


## Syntax
```
SqlStatementsExecuted :=   SessionInformation.SqlRowsRead()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  


## Return Value
*SqlStatementsExecuted*  
&emsp;Type: [BigInteger](../biginteger/biginteger-data-type.md)  
The amount of SQL rows read on the session, since the session started.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks

AL debugger also lets you monitor the number of SQL rows read. For more information, see [Debugging SQL behavior](../../devenv-debugging.md#DebugSQL).

## Example

The following code gets the number of SQL rows read for the session and displays the number in a message.

```
var
    SqlRowsRead := BigText;

begin

    SqlRowsRead := SessionInformation.SqlRowsRead();
    Message(Format(SqlRowsRead));
end;
```

## See Also
[SessionInformation Data Type](sessioninformation-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  