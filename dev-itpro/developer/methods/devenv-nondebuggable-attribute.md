---
title: "NonDebuggable Attribute"
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

# NonDebuggable Attribute
Specifies that a method or a variable is hidden from debugging in the sense that you cannot set breakpoints in the code or inspect any variables.

## Syntax  
```  
[NonDebuggable]
```
  
## Example
Setting the attribute on a method. Each method must be marked with `[NonDebuggable]`.

```
codeunit 50142 NoDebuggingOfMethod
{
    [NonDebuggable]
    local procedure MyProcedure()
    var
        myInt: Integer;
    begin
        //Make something happen
    end;
}

```

Setting the attribute on variables. Each variable must be marked as `[NonDebuggable]`.
```
codeunit 50143 NoDebuggingOfVar 
{
    local procedure MyProcedure()
    var
        [NonDebuggable]
        myInt: Integer;
    begin
        //Make something happen
    end;
}

```
  
## See Also  
[Debugging](../devenv-debugging.md)