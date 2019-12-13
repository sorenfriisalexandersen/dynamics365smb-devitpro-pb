---
title: "Record Data Type"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/14/2019
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
# Record Data Type
Is a complex data type.



The following methods are available on instances of the Record data type.

|Method name|Description|
|-----------|-----------|
|[FindFirst()](record-findfirst-method.md)|Finds the first record in a table based on the current key and filter.|
|[FindLast()](record-findlast-method.md)|Finds the last record in a table based on the current key and filter.|
|[FindSet([Boolean] [, Boolean])](record-findset-method.md)|Finds a set of records in a table based on the current key and filter.|
|[Get([Any,...])](record-get-method.md)|Gets a record based on values stored in primary key fields.|
|[Find([String])](record-find-method.md)|Finds a record in a table that is based on the values stored in keys.|
|[Next([Integer])](record-next-method.md)|Steps through a specified number of records and retrieves a record.|
|[Reset()](record-reset-method.md)|Removes all filters, including any special filters set by MARKEDONLY, and changes the current key to the primary key. Also removes any marks on the record and clears any AL variables on the record.|
|[SetCurrentKey(Any [, Any,...])](record-setcurrentkey-method.md)|Selects a key for a table.|
|[Ascending([Boolean])](record-ascending-method.md)|Gets or sets the order in which the system searches through a table.|
|[SetAscending(Any, Boolean)](record-setascending-method.md)|Sets the sort order for the records returned. Use this method after you have set the keys to sort after, using SETCURRENTKEY. The default sort order is ascending. You can use SETASCENDING to change the sort order to descending for a specific field, while the other fields in the specified key are sorted in ascending order.|
|[GetAscending(Any)](record-getascending-method.md)|Gets the sort order for the records returned. You can use GETASCENDING to identify the sort order of the specified field because fields can be sorted in ascending or descending order. For example, you can read data from an ODATA web service where the data is sorted in ascending order on the Name field but in descending order on the City field.|
|[LockTable([Boolean] [, Boolean])](record-locktable-method.md)|Locks a table to protect it from write transactions that conflict with each other.|
|[CalcFields(Any [, Any,...])](record-calcfields-method.md)|Calculates the FlowFields in a record. You specify which fields to calculate by using parameters.|
|[CalcSums(Any [, Any,...])](record-calcsums-method.md)|Calculates the total of a column in a table. You specify which fields to calculate by using parameters.|
|[SetAutoCalcFields([Any,...])](record-setautocalcfields-method.md)|Sets the FlowFields that you specify to be automatically calculated when the record is retrieved from the database.|
|[Count()](record-count-method.md)|Counts the number of records in a table.|
|[IsEmpty()](record-isempty-method.md)|Determines whether a table or a filtered set of records is empty.|
|[CountApprox()](record-countapprox-method.md)|Returns an approximate count of the number of records in the table, for example, for updating progress bars or displaying informational messages.|
|[TableName()](record-tablename-method.md)|Gets the name of a table.|
|[TableCaption()](record-tablecaption-method.md)|Gets the current caption of a table as a string.|
|[ChangeCompany([String])](record-changecompany-method.md)|Redirects references to table data from one company to another.|
|[CurrentKey()](record-currentkey-method.md)|Gets the current key of a database table.|
|[Consistent(Boolean)](record-consistent-method.md)|Marks a table as being consistent or inconsistent.|
|[GetPosition([Boolean])](record-getposition-method.md)|Gets a string that contains the primary key of the current record.|
|[SetPosition(String)](record-setposition-method.md)|Sets the fields in a primary key on a record to the values specified in the supplied string. The remaining fields are not changed.|
|[Init()](record-init-method.md)|Initializes a record in a table.|
|[Insert()](record-insert--method.md)|Inserts a record into a table without executing the code in the OnInsert trigger.|
|[Insert(Boolean)](record-insert-boolean-method.md)|Inserts a record into a table.|
|[Insert(Boolean, Boolean)](record-insert-boolean-boolean-method.md)|Inserts a record into a table.|
|[Modify([Boolean])](record-modify-method.md)|Modifies a record in a table.|
|[Delete([Boolean])](record-delete-method.md)|Deletes a record in a table.|
|[Rename(Any [, Any,...])](record-rename-method.md)|Changes the value of a primary key in a table.|
|[ModifyAll(Any, Any [, Boolean])](record-modifyall-method.md)|Modifies a field in all records within a range that you specify.|
|[DeleteAll([Boolean])](record-deleteall-method.md)|Deletes all records in a table that fall within a specified range.|
|[ReadPermission()](record-readpermission-method.md)|Determines whether a user is granted read permission to the table that contains a record. This method can test for both full read permission and partial read permission that has been granted with a security filter.|
|[WritePermission()](record-writepermission-method.md)|Determines whether a user can write to a table. This method can test for both full write permission and partial write permission that has been granted with a security filter. A write permission consists of Insert, Delete, and Modify permissions.|
|[ReadConsistency()](record-readconsistency-method.md)|Determines if the table supports read consistency.|
|[RecordLevelLocking()](record-recordlevellocking-method.md)|Determines whether the table supports record-level locking.|
|[Copy(var Record [, Boolean])](record-copy-method.md)|Copies a specified record's filters, views, automatically calculated FlowFields, marks, fields, and keys that are associated with the record from a table or creates a reference to a record.|
|[AddLink(String [, String])](record-addlink-method.md)|Adds a link to a record.|
|[DeleteLink(Integer)](record-deletelink-method.md)|Deletes a specified link from a record in a table.|
|[DeleteLinks()](record-deletelinks-method.md)|Deletes all of the links that have been added to a record.|
|[CopyLinks(var Record)](record-copylinks-table-method.md)|Copies all the links from a specified record.|
|[CopyLinks(RecordRef)](record-copylinks-recordref-method.md)|Copies all the links from a specified record.|
|[HasLinks()](record-haslinks-method.md)|Determines whether a record contains any links.|
|[SetRange(Any [, Any] [, Any])](record-setrange-method.md)|Sets a simple filter, such as a single range or a single value, on a field.|
|[SetFilter(Any, String [, Any,...])](record-setfilter-method.md)|Assigns a filter to a field that you specify.|
|[GetFilter(Any)](record-getfilter-method.md)|Gets a list of the filters within the current filter group that are applied to a field.|
|[GetFilters()](record-getfilters-method.md)|Gets a string that contains a list of the filters within the current filter group for all fields in a record. In addition, this method also returns the state of the MARKEDONLY method (Record).|
|[GetView([Boolean])](record-getview-method.md)|Gets a string that describes the current sort order, key, and filters on a table.|
|[SetView(String)](record-setview-method.md)|Sets the current sort order, key, and filters on a table.|
|[GetRangeMin(Any)](record-getrangemin-method.md)|Gets the minimum value in a range for a field.|
|[GetRangeMax(Any)](record-getrangemax-method.md)|Gets the maximum value in a range for a field.|
|[CopyFilter(Any, Any)](record-copyfilter-method.md)|Copies the filter that has been set for one field and applies it to another field.|
|[CopyFilters(var Record)](record-copyfilters-method.md)|Copies all the filters set by the SETFILTER method (Record) or the SETRANGE method (Record) from one record to another.|
|[HasFilter()](record-hasfilter-method.md)|Determines whether a filter is attached to a record within the current filter group.|
|[SetRecFilter()](record-setrecfilter-method.md)|Sets the values in the current key of the current record as a record filter.|
|[FilterGroup([Integer])](record-filtergroup-method.md)|Gets or sets the filter group that is applied to a table.|
|[SetPermissionFilter()](record-setpermissionfilter-method.md)|Applies the user's security filter.|
|[Mark([Boolean])](record-mark-method.md)|Marks a record. You can also use this method to determine whether a record is marked.|
|[ClearMarks()](record-clearmarks-method.md)|Removes all the marks from a record.|
|[MarkedOnly([Boolean])](record-markedonly-method.md)|Activates a special filter. After you use this function, your view of the table includes only records marked by this function.|
|[Validate(Any [, Any])](record-validate-method.md)|Calls the OnValidate trigger for the field that you specify.|
|[TestField(Any)](record-testfield-joker-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, Boolean)](record-testfield-joker-boolean-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, Integer)](record-testfield-joker-integer-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, BigInteger)](record-testfield-joker-biginteger-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, Decimal)](record-testfield-joker-decimal-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, Guid)](record-testfield-joker-guid-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, Text)](record-testfield-joker-text-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, Label)](record-testfield-joker-label-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, TextConst)](record-testfield-joker-textconst-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, Code)](record-testfield-joker-code-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, String)](record-testfield-joker-string-method.md)|Tests whether the contents of a field match a given value.|
|[TestField(Any, Any)](record-testfield-joker-joker-method.md)|Tests whether the contents of a field match a given value.|
|[FieldError(Any [, String])](record-fielderror-method.md)|Stops the execution of the code causing a run-time error, and creates an error message for a field.|
|[TransferFields(var Record [, Boolean])](record-transferfields-table-boolean-method.md)|Copies all matching fields in one record to another record.|
|[TransferFields(var Record, Boolean, Boolean)](record-transferfields-table-boolean-boolean-method.md)|Copies all matching fields in one record to another record.|
|[FieldName(Any)](record-fieldname-method.md)|Gets the name of a field as a string.|
|[FieldCaption(Any)](record-fieldcaption-method.md)|Gets the current caption of the specified field as a string.|
|[FieldActive(Any)](record-fieldactive-method.md)|Checks whether a field is enabled.|
|[FieldNo(Any)](record-fieldno-method.md)|Gets the number assigned to a field in the table description.|
|[Relation(Any)](record-relation-method.md)|Determines the table relationship of a given field.|
|[SecurityFiltering([SecurityFilter])](record-securityfiltering-method.md)||
|[RecordId()](record-recordid-method.md)||
|[IsTemporary()](record-istemporary-method.md)|Determines whether a record refers to a temporary table.|
|[CurrentCompany()](record-currentcompany-method.md)|Gets the current company of a database table record.|
|[GetBySystemId(Guid)](record-getbysystemid-method.md)|Gets a record by its SystemId.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  