---
title: Filtering in Query Objects
description: Specify filters in a query to restrict the data in the resulting dataset. A filter applies conditions on fields in a table associated with the query.
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: jswymer
---
# Filtering in Query Objects

You specify filters in a query to restrict the data in the resulting dataset. A filter applies conditions on fields in a table that is associated with the query. For a field to be included in the resulting dataset, a field must meet the conditions of the filter.  

## Different ways to filter a Query dataset

You can set up filters on a field directly in the query object, or you can use the filter methods that are outlined in the following table.  

||Filter|Description|  
|------------|------------|-----------------|  
|In query object|Filter on a Data item|You can set the [DataItemTableFilter property](properties/devenv-dataitemtablefilter-property.md) of a data item to filter on a field in the table of the data item. You can apply the filter to any field in the table, not just fields that are defined as columns in the resulting dataset. A data item filter cannot be overwritten from AL code.|  
||Filter on a Column|You can set the [ColumnFilter property](properties/devenv-columnfilter-property.md) of a `column` control to filter on the source field of the column. A filter on a column can be overwritten by the [SETFILTER](methods-auto/record/record-setfilter-method.md) and [SETRANGE](methods-auto/record/record-setrange-method.md) methods from AL code.|  
||Add a filter row|A filter row lets you add a filter on a field that will not be included in the resulting dataset, but can be changed from AL code. To set up a row filter add a `filter` control referencing the filed that you want to filter and then set its [ColumnFilter Property](properties/devenv-columnfilter-property.md). A filter row is like a data item filter except a filter on a filter row can be overwritten by the [SETFILTER](methods-auto/record/record-setfilter-method.md) and [SETRANGE](methods-auto/record/record-setrange-method.md) methods from AL code.|  
|AL filter method calls|[SETFILTER method](methods-auto/query/queryinstance-setfilter-method.md)|You can call the **SETFILTER** method from AL code to set a filter on a field that is exposed through a column or filter row. The filter that is set by the **SETFILTER** method will overwrite any filter that is applied to a column or filter row on the same field by the [ColumnFilter Property](properties/devenv-columnfilter-property.md).|  
||[SETRANGE method](methods-auto/query/queryinstance-setrange-method.md)|You can call the **SETRANGE** method from AL code to set a filter on a field that is exposed through a column or filter row. The filter that is set by the **SETRANGE** method will overwrite any filter that is applied to column or filter row on the same field.|  

## Filtering on data items in a Query object

To specify filters on a data item, you set the [DataItemTableFilter property](properties/devenv-dataitemtablefilter-property.md) of a data item. **DataItemTableFilter** property has the following syntax:

```
DataItemTableFilter = String;
```

Where `String` is the filter expression.

You can apply a filter on any field in a table, not just those fields that are represented by a column in the query object.

A data item filter is static which means that it cannot be overwritten by the [ColumnFilter Property](properties/devenv-columnfilter-property.md), `filter` controls or by the [SETFILTER](methods-auto/record/record-setfilter-method.md) or [SETRANGE](methods-auto/record/record-setrange-method.md) methods in AL code. If one of these filter types is applied to the same field as the data item filter, then the filters are combined. In logical terms, this combination corresponds to an "AND" operation. For example, if the data item filter applies a filter on a field to include values greater than 10 \(>10\) and a column filter applies a filter on the same field to include values less than fifty \(\<50\), then the resultant filter includes values that are greater than 10 and less than fifty \(10\< value \<50\).  

 The [DataItemTableFilter Property](properties/devenv-dataitemtablefilter-property.md) corresponds to a WHERE clause in an SQL SELECT statement. For more information, see [Equivalent SQL SELECT Statements for Query Filters](devenv-query-filters.md#SQL).  

### Example

The following query object links table `18 Customer` and table `37 Sales Line` to get the number of line items in each sales for customers. The **DataItemTableFilter** property is used to only include rows in which the number of line items is greater than 10.  

```
query 50100 "Customer_Sales_Quantity"
{
    QueryType = Normal;

    elements
    {
        dataitem(C; Customer)
        {
            column(Customer_Number; "No.")
            {
            }

            column(Customer_Name; Name)
            {
            }

            dataitem(SL; "Sales Line")
            {
                DataItemLink = "Sell-to Customer No." = c."No.";
                SqlJoinType = InnerJoin;
                DataItemTableFilter = Quantity = filter(> 10);

                column(Qty; Quantity)
                {
                }
            }
        }
    }
}
```

## Filtering on columns and filter rows in Query object

Unlike data item filters, filters on a column or filter row are dynamic and can be overwritten from AL code at runtime by a call to the [SETFILTER](methods-auto/record/record-setfilter-method.md) or [SETRANGE](methods-auto/record/record-setrange-method.md) method, if the method sets a filter on the same field.  

You use filters on a column to filter on fields that are included in the dataset. To apply a filter on a column, you set the [ColumnFilter Property](properties/devenv-ColumnFilter-Property.md) of the column.  You can apply a filter on any column, including aggregated columns that are applied an aggregate method by the [Method Property](properties/devenv-Method-Property.md).  The **ColumnFilter** property has the following syntax:

```
ColumnFilter = String;
```

where `String` is the filter expression.

You use a filter row when you want to filter the query on a field, but you do not want to include the field in the dataset. For example, you might want to filter a date field on a specific date, but you do not want to include the date in the dataset. To set up a filter row similar to columns of a data item. First, you add `filter` element that specifies the table field on which you want to filter, then you add the **ColumnFilter** property to set the conditions of the filter.

### Example

The following query object links the `Customer` table and the `Sales Line` table and retrieves the total quantity of line items ordered for each customer. The query includes the following filters.  

-  A filter on the `Qty` column to include only records from the `Sales Line` table where the total quantity is less than 50.  

- A filter on filter row for the `Location Code` field of the Sales Line table that includes only records where the location code is WHITE. 

```
query 50100 "Customer_Sales_Quantity"
{
    QueryType = Normal;

    elements
    {
        dataitem(C; Customer)
        {
            column(Customer_Number; "No.")
            {
            }

            column(Customer_Name; Name)
            {
            }

            dataitem(SL; "Sales Line")
            {
                DataItemLink = "Sell-to Customer No." = c."No.";
                SqlJoinType = InnerJoin;
                DataItemTableFilter = Quantity = filter(> 10);

                column(Qty; Quantity)
                {
                    Method = Sum;
                    ColumnFilter = Qty = filter(< 50);
                }

                filter(Location_Code; "Location Code")
                {
                    ColumnFilter = Location_Code = const('White');
                }
            }
        }
    }
} 

```

In an SQL SELECT statement, filters on a column or filter row that do not apply an aggregate method, as with the `Location_Code` filter row in the example, would correspond to a WHERE clause. Filters on a columns or filter rows that do apply a totals method, as with the `Quantity` column in the example, would correspond to a HAVING clause. For more information, see [Equivalent SQL SELECT Statements for Query Filters](devenv-query-filters.md#SQL).  

## Filtering using SETFILTER and SETRANGE methods

AL code includes the [SETFILTER](methods-auto/record/record-setfilter-method.md) and [SETRANGE](methods-auto/record/record-setrange-method.md) methods that you can use to apply a filter on a field that is represented as a column or filter row in a query. The **SETFILTER** and **SETRANGE** methods enable you to set filters programmatically on a query at runtime. You use the **SETRANGE** method to filter on a range of values in a column or filter row. The **SETFILTER** method is more versatile than the **SETRANGE** method and enables you to filter a field based on a filter expression.  

These methods will overwrite any filter on the same field that is set on a column or filter row by the `ColumnFilter` property. If a **SETFILTER** or **SETRANGE** method filters on the same field as a filter on a data item, as specified by the [DataItemTableFilter Property](properties/devenv-dataitemtablefilter-property.md), then the method filter and **DataItemTableFilter** property filter are combined.  

### Calling the SETFILTER and SETRANGE methods

You can call the **SETFILTER** and **SETRANGE** method from the AL code of the [!INCLUDE[prodshort](includes/prodshort.md)] object that runs the query object or from the [OnBeforeOpen Trigger](triggers/devenv-onbeforeopen-trigger.md) of the query object.  

To call the **SETFILTER** method, you use the following code.  

```  
Query.SETFILTER(Column, String)  
```  

To call the **SETRANGE** method, you use the following code.  

```  
Query.SETRANGE(Column, FromValue, ToValue)  
```
 
where:
-   `Query` is a variable of the Query type that specifies the query object.  

-   `Column` is the name of the column or filter row as defined by its Name property.  

-   `String` is the filter expression.  

-   `FromValue` is the lower value of the range.  

-   `ToValue` is the higher value of the range.  

For more information about these methods and important behavior, see [SETFILTER method](methods-auto/query/queryinstance-setfilter-method.md) and [SETRANGE method \(Query\)](methods-auto/query/queryinstance-setrange-method.md).  

### Example

Referring to the query example in the previous sections, you can add the following code to the **OnBeforeOpen** trigger of the query object to change the filters on the `Quantity` column and the  `Location\_Code` filter row to include quantities of in the range of 10 to 50 and a location code of RED.

```  
trigger OnBeforeOpen()
begin
    currQuery.SETRANGE(Qty, 10, 50);
    currQuery.SETFILTER(Location_Code, '=RED');
end;  
```

##  <a name="SQL"></a> Equivalent SQL SELECT Statements for Query Filters

If you are familiar with SQL, then it is helpful to know how filtering in [!INCLUDE[prodshort](includes/prodshort.md)] queries relates to SQL statements. To specify filters in an SQL statement, you use WHERE and HAVING clauses. The WHERE clause filters on fields. The HAVING clause filters on the results that have aggregated values as applied by of a totals method.  

The following example shows the corresponding SQL SELECT statement for the previous data item filter example that links the `Customer` and `Sales Line` tables and filters on the `Quantity` field.  

```  
SELECT Customer."No.", Customer.Name, "Sales Line".Quantity  
FROM Customer LEFT OUTER JOIN "Sales Line"  
ON Customer."No." = "Sales Line".Sell-to Customer No.  
WHERE "Sales Line"."Quantity" > 10  
```  

The following example shows the corresponding SQL SELECT statement for the previous column and filter row example that links the `Customer` and `Sales Line `tables and filters on the `Location Code` field and the total sum of the `Quantity` field.  

```  
SELECT Customer."No.", Customer.Name, SUM("Sales Line".Quantity) as Qty  
FROM Customer LEFT OUTER JOIN "Sales Line"  
  ON Customer."No." = "Sales Line".Sell-to Customer No.  
WHERE "Sales Line"."Location Code" = WHITE  
GROUP BY Customer."No."  
HAVING Qty  50  
```  

## See Also

 [Query Object](devenv-query-object.md)  
 [Aggregating Data](devenv-query-totals-grouping.md)  
 [SETFILTER method](methods-auto/query/queryinstance-setfilter-method.md)  
 [SETRANGE method](methods-auto/query/queryinstance-setrange-method.md)
