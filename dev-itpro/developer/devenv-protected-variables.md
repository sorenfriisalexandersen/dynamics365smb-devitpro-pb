---
title: "Protected Variables"
ms.custom: na
ms.date: 11/20/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: SusanneWindfeldPedersen
---

# Protected Variables

[!INCLUDE[2019_releasewave2.md](../includes/2019_releasewave2.md)]

The `protected` keyword can be used to make variables accessible between tables and table extensions and between pages and page extensions. If you want to only expose some variables as `protected`, you must create two sections of `var` declarations. See the syntax below.

## Syntax
```
protected var
        myInt: Integer;

var
        myLocalInt: Integer;
```

## Example
page 500100 MyPage
{
    SourceTable = Customer;
    PageType = Card;

    layout
    {
        area(Content)
        {
            group(General)
            {
                field(Name; Name)
                {
                    ApplicationArea = All;
                }
            }
            group(Advanced)
            {
                Visible = ShowBalance;

                field(Balance; Balance)
                {
                    ApplicationArea = All;
                }
            }
        }
    }

    protected var
        [InDataSet]
        ShowBalance: Boolean;
}

pageextension 500101 MyPageExt extends MyPage
{
    layout
    {
        addlast(Content)
        {
            group(MoreBalance)
            {
                Visible = ShowBalance; // ShowBalance from MyPage

                field("Balance (LCY)"; "Balance (LCY)")
                {
                    ApplicationArea = All;
                }
            }
        }

    }

    actions
    {
        addlast(Navigation)
        {
            action(ToggleBalance)
            {
                ApplicationArea = All;
                trigger OnAction()
                begin
                    ShowBalance := not ShowBalance; // Toggle ShowBalance from MyPage.
                end;
            }
        }
    }
}


## See Also  
[AL Method Reference](methods/devenv-al-method-reference.md)   
[Properties](properties/devenv-properties.md)  
[Access Property](properties/devenv-access-property.md)  
[Extensible Property](properties/devenv-extensible-property.md)
