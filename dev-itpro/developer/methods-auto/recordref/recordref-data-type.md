---
title: "RecordRef Data Type"
ms.author: solsen
ms.custom: na
ms.date: 10/09/2019
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
# RecordRef Data Type
References a record in a table.



The following methods are available on instances of the RecordRef data type.

|Method name|Description|
|-----------|-----------|
|[Open(Integer [, Boolean] [, String])](recordref-open-method.md)|Causes a RecordRef variable to refer to a table, which is identified by its number in a particular company.|
|[Close()](recordref-close-method.md)|Closes the current page or table.|
|[GetTable(Record)](recordref-gettable-method.md)|Gets the table of a Record variable and causes the RecordRef to refer to the same table.|
|[SetTable(Record)](recordref-settable-method.md)|Sets the table to which a Record variable refers as the same table as a RecordRef variable.|
|[Duplicate()](recordref-duplicate-method.md)|Duplicates the table that contains the RecordRef.|
|[IsTemporary()](recordref-istemporary-method.md)|Determines whether a RecordRef refers to a temporary table.|
|[CurrentCompany()](recordref-currentcompany-method.md)|Gets the current company of a database table referred to by a RecordRef.|
|[Get(RecordId)](recordref-get-method.md)|Gets a record based on the ID of the record.|
|[Find([String])](recordref-find-method.md)|Finds a record in a table based on the values stored in the key fields.|
|[Next([Integer])](recordref-next-method.md)|Steps through a specified number of records and retrieves a record.|
|[FindFirst()](recordref-findfirst-method.md)|Finds the first record in a table based on the current key and filter.|
|[FindLast()](recordref-findlast-method.md)|Finds the last record in a table based on the current key and filter.|
|[FindSet([Boolean] [, Boolean])](recordref-findset-method.md)|Finds a set of records in a table based on the current key and filter. FINDSET can only retrieve records in ascending order.|
|[Reset()](recordref-reset-method.md)|Removes all filters, including any special filters set by the MARKEDONLY method (Record) and changes the current key to the primary key. Also removes any marks on the record and clears any AL variables on the record.|
|[Ascending([Boolean])](recordref-ascending-method.md)|Changes or checks the order in which a search through the table that is referred to by RecordRef will be performed.|
|[LockTable([Boolean] [, Boolean])](recordref-locktable-method.md)|Locks a table to protect it from write transactions that conflict with each other.|
|[Count()](recordref-count-method.md)|Counts the number of records that are in the filters that are currently applied to the table referred to by the RecordRef.|
|[IsEmpty()](recordref-isempty-method.md)|Determines whether any records exist in a filtered set of records in a table.|
|[CountApprox()](recordref-countapprox-method.md)|Gets an approximate count of the number of records in the table|
|[CurrentKey()](recordref-currentkey-method.md)|Gets the current key of the table referred to by the RecordRef. The current key is returned as a string.|
|[CurrentKeyIndex([Integer])](recordref-currentkeyindex-method.md)|Gets or sets the current key of the table referred to by the RecordRef. The current key is set or returned as a number. This first key = 1, and so on. If RecordRef does not have an active record, CURRENTKEYINDEX will return -1. If this value is then passed to KEYINDEX, an index out of bounds error will occur. Therefore it is important to implement a check of the RecordRef parameter.|
|[GetPosition([Boolean])](recordref-getposition-method.md)|Gets a string that contains the primary key of the current record.|
|[SetPosition(String)](recordref-setposition-method.md)|Sets the fields in a primary key on a record to the values specified in the String parameter. The remaining fields are not changed.|
|[Number()](recordref-number-method.md)|Gets the table ID (number) of the table that contains the record that was referred to by the RecordRef.|
|[Name()](recordref-name-method.md)|Identifies the name of the table|
|[Caption()](recordref-caption-method.md)|Gets the caption of the table that is currently selected. Returns an error if no table is selected.|
|[RecordId()](recordref-recordid-method.md)|Gets the RecordID of the record that is currently selected in the table. If no table is selected, an error is generated.|
|[ChangeCompany([String])](recordref-changecompany-method.md)|Redirects references to table data from one company to another.|
|[Init()](recordref-init-method.md)|Initializes a record in a table.|
|[Insert()](recordref-insert--method.md)|Inserts a record into a table without executing the code in the OnInsert trigger.|
|[Insert(Boolean)](recordref-insert-boolean-method.md)|Inserts a record into a table.|
|[Insert(Boolean, Boolean)](recordref-insert-boolean-boolean-method.md)|Inserts a record into a table.|
|[Modify([Boolean])](recordref-modify-method.md)|Modifies a record in a table.|
|[Delete([Boolean])](recordref-delete-method.md)|Deletes a record in a table.|
|[DeleteAll([Boolean])](recordref-deleteall-method.md)|Deletes all records in a table that fall within a specified range.|
|[ReadPermission()](recordref-readpermission-method.md)|Determines if you can read from a table.|
|[WritePermission()](recordref-writepermission-method.md)|Determines if you can write to a table.|
|[ReadConsistency()](recordref-readconsistency-method.md)|Gets a value indicating whether read consistency is enabled.|
|[RecordLevelLocking()](recordref-recordlevellocking-method.md)|Gets a value indicating whether record level locking is enabled.|
|[AddLink(String [, String])](recordref-addlink-method.md)|Adds a link to a record in a table.|
|[DeleteLink(Integer)](recordref-deletelink-method.md)|Deletes a specified link from a record in a table.|
|[DeleteLinks()](recordref-deletelinks-method.md)|Deletes all of the links that have been added to a record.|
|[CopyLinks(Record)](recordref-copylinks-table-method.md)|Copies all the links from a particular record.|
|[CopyLinks(RecordRef)](recordref-copylinks-recordref-method.md)|Copies all the links from a particular record.|
|[CopyLinks(Variant)](recordref-copylinks-variant-method.md)|Copies all the links from a particular record.|
|[HasLinks()](recordref-haslinks-method.md)|Determines whether a record contains any links.|
|[FieldCount()](recordref-fieldcount-method.md)|Gets the number of fields in the table that are currently selected or returns the number of fields that have been defined in a key. Returns an error if no table or no key is selected.|
|[Field(Integer)](recordref-field-method.md)|Gets a FieldRef for the field that has the number FieldNo in the table that is currently selected. If no field has this number, the method returns an error.|
|[FieldExist(Integer)](recordref-fieldexist-method.md)|Determines if the field that has the number FieldNo exists in the table that is referred to by the RecordRef. Returns an error if no table is currently selected.|
|[FieldIndex(Integer)](recordref-fieldindex-method.md)|Gets the FieldRef of the field that has the specified index in the table that is referred to by the RecordRef.|
|[KeyCount()](recordref-keycount-method.md)|Gets the number of keys that exist in the table that is referred to by the RecordRef. Returns an error if no table is selected.|
|[KeyIndex(Integer)](recordref-keyindex-method.md)|Gets the KeyRef of the key that has the index specified in the table that is currently selected. The key can be composed of fields of any supported data type. Data types that are not supported include BLOBs, FlowFilters, variables, and functions. If the sorting key is set to a field that is not part of a key, then the KEYINDEX is -1.|
|[GetFilters()](recordref-getfilters-method.md)|Determines which filters have been applied to the table referred to by the RecordRef.|
|[GetView([Boolean])](recordref-getview-method.md)|Returns a string that describes the current sort order, key, and filters on a table.|
|[SetView(String)](recordref-setview-method.md)|Sets the current sort order, key, and filters on a table.|
|[HasFilter()](recordref-hasfilter-method.md)|Determines whether a filter has been applied to the table that the RecordRef refers to.|
|[SetRecFilter()](recordref-setrecfilter-method.md)|Sets a filter on a record that is referred to by a RecordRef.|
|[FilterGroup([Integer])](recordref-filtergroup-method.md)|Changes the filter group that is being applied to the table. You can also use this method to return the number of the current filtergroup. You cannot return the number of the filtergroup and set a new filtergroup at the same time.|
|[SetPermissionFilter()](recordref-setpermissionfilter-method.md)|Applies the user's security filter to the referenced record. The security filter is combined with any other filters that are placed on the record with SetFilter or SetRange. The combined filter will not include any records outside the range of the security filter and this will prevent a runtime permission error from occuring when the record is read. If the permission filter is not set, an error can occur if you attempt to read a record that is outside the range of the user's security filter.|
|[Rename(Any [, Any,...])](recordref-rename-method.md)|Changes the value of a primary key in a table.|
|[SecurityFiltering([SecurityFilter])](recordref-securityfiltering-method.md)|Gets or sets how security filters are applied to the RecordRef.|
|[SystemIdNo()](recordref-systemidno-method.md)|Gets the field number that is used by the SystemId field. The SystemId field is a system field that the platform adds to all table objects.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)

 
 
The RecordRef object can refer to any table in the database. Use the [OPEN method](recordref-open-method.md) to use the table number to select the table that you want to access, or use the [GETTABLE method](recordref-gettable-method.md) to use another record variable to select the table that you want to access.  
  
 If one RecordRef variable is assigned to another RecordRef variable, then they both refer to the same table instance. 

## See Also  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  