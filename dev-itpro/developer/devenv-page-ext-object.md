---
title: "Page Extension Object"
description: "Description of the page extension object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 10/24/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
ms.author: solsen
---

# Page Extension Object
The page extension object extends a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] page object and adds or overrides the functionality.

The structure of a page is hierarchical and breaks down into three sections. The first block contains metadata for the overall page; the type of the page and the source table it is showing data from. The next section; the layout, describes the visual parts on the page. The final section details the actions that are published on the page.

For more information about the Page and Page Extension objects, see [Pages Overview](devenv-pages-overview.md).

> [!IMPORTANT]  
> Only pages with the [Extensible Property](properties/devenv-extensible-property.md) set to **true** can be extended.

> [!NOTE]  
> Extension objects can have a name with a maximum length of 30 characters.

> [!IMPORTANT]  
> The API page type should not be extended by creating a page extension object. Instead, create a new API by adding a [page object](devenv-page-object.md).

## Snippet support
Typing the shortcut `tpageext` will create the basic layout for a page extension object when using the [!INCLUDE[d365al_ext_md](../includes/d365al_ext_md.md)] in Visual Studio Code.

[!INCLUDE[intelli_shortcut](includes/intelli_shortcut.md)]

## Views
Views in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] are used on list pages to define a different view of the data on a given page. Views can be defined for [Pages](devenv-page-object.md), [Page Extensions](devenv-page-ext-object.md), and [Page Customization](devenv-page-customization-object.md). For more information, see [Views](devenv-views.md).

## Page extension examples
In the following example, we use a table extension to extend the Customer table with a new field named `ShoeSize` of the datatype Integer. Then we create a page extension object that extends the Customer Card page object by adding a field control `ShoeSize` to the `General` group on the page. The field control is added as the last control in the group using the `addlast` method. The example also illustrates how to add a display-only control to the page.
In the actions area, you can see what the syntax looks like for actions that execute triggers and actions that run objects.

```
tableextension 50115 RetailWinterSportsStore extends Customer
{
    fields
    {
        field(50116;ShoeSize;Integer)
        {
            Caption = 'ShoeSize';
            
            trigger OnValidate();
            begin
                if (rec.ShoeSize < 0) then
                begin
                   message('Shoe size not valid: %1', rec.ShoeSize);
                end;
            end;
        }
    }

    procedure HasShoeSize() : Boolean;
    begin
        exit(ShoeSize <> 0);
    end;

    trigger OnBeforeInsert();
    begin
        if not HasShoeSize then
            ShoeSize := Random(42);
    end;
}

pageextension 50110 CustomerCardExtension extends "Customer Card"
{
    layout
    {
        addlast(General)
        {
            // control with underlying datasource
            field("Shoe Size"; ShoeSize)
            {
                ApplicationArea = All;

                trigger OnValidate();
                begin
                    if ShoeSize < 10 then
                        Error('Feet too small');
                end;
            }

            // display-only control (without underlying datasource)
            field(ShoesInStock; 10)
            {
                ApplicationArea = All;
                Caption = 'Shoes in stock';

            }
        }

        modify("Address 2")
        {
            Caption = 'New Address 2';
        }
    }

    actions
    {
        addlast(Creation)
        {
            group(MyActionGroup)
            {
                Action(MyAction1)
                {
                    ApplicationArea = All;
                    Caption = 'Hello!';

                    trigger OnAction();
                    begin
                        Message('My message');
                    end;
                }

                Action(MyAction2)
                {
                    ApplicationArea = All;
                    
                    // Run page to test how actions work
                    RunObject = page "Absence Registration";
                    
                }
            }
        }
    }
}
```

You can reference Report and XMLPort objects and use these objects in the **RunObject** property, as well as, declare variables of the types **Report** and **XMLPort** and call AL methods on them. This page extension object extends the Customer List page object by adding two actions; the first action calls the **Customer - List** report, the second action calls the **Export Contact** xmlport.

```
pageextension 50114 AddCustomerReport extends "Customer List"
{
    actions
    {
        AddLast("&Customer")
        {
            action("Customer List Report")
            {
                trigger OnAction();
                var
                    rep : Report "Customer - List";
                begin
                    rep.Run;
                end;
            }

            action("Export Contact List")
            {
                trigger OnAction();
                var
                    xml : XmlPort "Export Contact";
                begin
                    xml.Run;
                end;
            }
        }
    }
}
```

## See Also  
[Page Object](devenv-page-object.md)  
[Views](devenv-views.md)  
[Page and Page Extension Properties](properties/devenv-page-property-overview.md)    
[Developing Extensions](devenv-dev-overview.md)  
[AL Development Environment](devenv-reference-overview.md)  
