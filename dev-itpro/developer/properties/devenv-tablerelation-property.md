---
title: "TableRelation Property"
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

# TableRelation Property

Sets relationships (links) to other tables. For example, if you want to provide a lookup into another table, set the name of that table on this property.  
  
## Applies To  
  
- Table Fields  
- Page Fields  
  
## Remarks

The `TableRelation` property lets you establish lookups into other tables. For example, on the Item card you can select a vendor from who you usually purchase an item. This is done through a table relationship.  
  
This property is also used to define where to look to validate entries.  
  
In addition, when you choose the option to test the relationships between primary and secondary indexes, this property defines what to test.

## Example

This example shows a simple application of the `TableRelation` property for creating a `Vendors` sub-table by filtering between the records to include only the ones where the purchase expenses are higher than 10,000. 

```
table 50100 "Main Vendors"
{
  fields
  {
    field(1; "Vendor No."; Code[20])
    {
      DataClassification = ToBeClassified;
      TableRelation = Vendor."No." where ("Balance (LCY)" = filter (>= 10000));
    {

    field(2; "Vendor Name"; Text[150])
    {
      DataClassification = ToBeClassified;
      FieldClass = FlowField;
      CalcFormula = lookup (Vendor.Name where ("No." = field ("Vendor No.")));
    }
  }
}
```

Moreover, the `TableRelation` property can be modified through a [table extension](../devenv-table-ext-object.md). Modifications to the `TableRelation` are additive and evaluated after the existing value. The primary use case is conditional table relations based on conditional enums. The following example illustrates how to define first, an enum, and then a table setting a `TableRelation`. 

```
enum 50120 TypeEnum
{
  Extensible = true;

  value(0; Nothing) { }
  value(1; Customer) { }
  value(2; Item) { }
}

table 50120 TableWithRelation
{
  fields
  {
    field(1; Id; Integer) { }
    field(2; Type; enum TypeEnum) { }
    field(3; Relation; Code[20])
    {
      TableRelation =
        if (Type = const (Customer)) Customer
        else if (Type = const (Item)) Item;
    }
  }
}

```
The next code sample implements a table extension of the table defined above and an enum extension. The combined table relation is evaluated top-down. That means that the first unconditional relation will prevail, meaning that you cannot change an existing `TableRelation` from Customer to Item, since the original table relation is unconditional. 

```
enumextension 50133 TypeEnumExt extends TypeEnum
{
  value(10; Resource) { }
}

tableextension 50135 TableWithRelationExt extends TableWithRelation
{
  fields
  {
    modify(Relation)
    {
      TableRelation = if (Type = const (Resource)) Resource;
    }
  }
}
```

  
## See Also

[ValidateTableRelation Property](devenv-validatetablerelation-property.md)  
[TestTableRelation Property](devenv-testtablerelation-property.md)