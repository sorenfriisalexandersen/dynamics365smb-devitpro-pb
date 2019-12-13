---
title: "Get, Find, and Next Methods"
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

# Get, Find, and Next Methods
The following methods are used to search for records:  
  
- Get
- Find  
- Next  
  
These methods are some of the most frequently used AL methods. When you search for records, you must know the difference between Get and Find and to know how to use Find and Next in conjunction.  
  
## Get method  
The [Get Method (Record)](methods-auto/record/record-get-method.md) retrieves one record based on values of the primary key fields.  
  
Get has the following syntax.  
  
```  
[Ok :=] Record.Get([Value],...)  
```  
  
For example, if the **No.** field is the primary key of the **Customer** table and if you have created a record variable called **CustomerRec** that has a subtype of Customer, then you can use Get in the following way.  
  
```  
CustomerRec.Get('4711');  
```  
  
The result is that the record of customer 4711 is retrieved.  
  
Get produces a run-time error if it fails and the return value is not checked by the code. In the previous example, the actual code that you write should resemble the following.  
  
```  
if CustomerRec.GET('4711') then
.... // Do some processing.  
else  
.... // Do some error processing.  
```  
  
Get searches for the records, regardless of the current filters, and it does not change any filters. Get always searches through all the records in a table.  

## GetBySystemId method

[!INCLUDE[2019_releasewave2](../includes/2019_releasewave2.md)]

The [GetBySystemId(Guid)](methods-auto/record/record-getbysystemid-method.md) retrieves a record based on the value of its **SystemId** field.   
  
GetBySystemId has the following syntax:  
  
```
RecordExists :=   Record.GetBySystemId(SystemId: Guid)
``` 
  
The following example gets the record that has the SystemId `5286305A-08A3-E911-8180-001DD8B7338E`:

```
var
    Customer: Record Customer;
    Text000: TextConst ENU = 'Customer was found.';
begin
    If Customer.GetBySystemId('{5286305A-08A3-E911-8180-001DD8B7338E}') then
    Message(Text000);
end;
```  

## Find methods  
The [Find Method (Record)](methods-auto/record/record-find-method.md) locates a record in a table that is based on the values stored in the keys.  
  
Find has the following syntax.  
  
```  
Ok := Record.Find([Which])  
```  
  
The *Which* parameter specifies how to perform the search. You can search for values that are greater than, less than, or equal to the key value, or for the first or last record in a table.  
  
The important differences between Get and Find are as follows:  
  
- Find uses the current filters.  
  
- Find can look for records where the key value is equal to, greater than, or smaller than the search string.  
  
- Find can find the first or the last record, depending on the sort order defined by the current key.  
  
When you are developing applications in a relational database, there are often one-to-many relationships defined between tables. An example could be the relationship between an **Item Variant** table, which registers items, and a **Sales Line** table, which registers the detailed lines from sales orders. One record in the **Sales Line** table can only be related to one item, but each item can be related to any number of sales line records. You would not want an item record to be deleted as long as there are still open sales orders that include the item. You can use Find to check for open sales orders.  
  
The OnDelete trigger of the **Item Variant** table includes the following code that illustrates using Find.  
  
```  
SalesOrderLine.SetCurrentKey(Type, "No.");
SalesOrderLine.SetRange(Type, SalesOrderLine.Type::Item);
SalesOrderLine.SetRange("No.", "Item No.");
SalesOrderLine.SetRange("Variant Code", Code);
if not SalesOrderLine.IsEmpty then
    Error(Text001, Code, SalesOrderLine.TableCaption);  
```  
  
If you want to find the first record in a table or set, then use the [FindFirst Method (Record)](methods-auto/record/record-findfirst-method.md). If you want to find the last record in a table or set, then use the [FindLast Method (Record)](methods-auto/record/record-findlast-method.md).  
  
## Next method  
The [Next Method (Record)](methods-auto/record/record-next-method.md) is often used with FIND to step through the records of a table.  
  
Next has the following syntax.  
  
```  
Steps := Record.Next([Steps])  
```  
  
In the following example, Find is used to go to the first record of the table. Next is used to step through every record, until there are no more. When there are no more records, Next returns 0 (zero).  
  
```  
if (Rec.FindSet) then
repeat
  // process record  
until (Rec.Next = 0);  
```

## See Also
[AL Methods](methods-auto/library.md)  
[SystemId Field](devenv-table-object.md#systemid)
