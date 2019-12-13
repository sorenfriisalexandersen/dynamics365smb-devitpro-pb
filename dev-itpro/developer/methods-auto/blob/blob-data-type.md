---
title: "Blob Data Type"
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
# Blob Data Type
Is a complex data type. Variables of this data type differ from normal numeric and string variables in that BLOBs have a variable length. The maximum size of a BLOB(binary large object) is 2 GB.



The following methods are available on instances of the Blob data type.

|Method name|Description|
|-----------|-----------|
|[HasValue()](blob-hasvalue-method.md)|Determines whether a binary large object (BLOB) has a value.|
|[Length()](blob-length-method.md)|Returns the number of bytes in the binary large object (BLOB).|
|[Import(String)](blob-import-method.md)|Imports a binary large object (BLOB) from a file.|
|[Export(String)](blob-export-method.md)|Exports a binary large object (BLOB) to a file.|
|[CreateInStream(InStream [, TextEncoding])](blob-createinstream-method.md)|Creates an InStream object for a binary large object (BLOB). This enables you to read data from the BLOB.|
|[CreateOutStream(OutStream [, TextEncoding])](blob-createoutstream-method.md)|Creates an OutStream object for a binary large object (BLOB). This enables you to write data to the BLOB.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 Use BLOBs to store memos (text), pictures (bitmaps), or user-defined types.  

> [!NOTE]  
>  You cannot view text that is stored in BLOBs from the development environment.  

 You can read from and write to BLOBs by creating input and output streams, respectively. To do so, use [CREATEINSTREAM method (BLOB)](blob-createinstream-method.md) and [CREATEOUTSTREAM method (BLOB)](blob-createoutstream-method.md).  

<!--
To optimize performance, when you access a record that has a BLOB field, the data in the BLOB is not always read into memory. You must call the [CALCFIELDS method (Record)](../../methods/devenv-calcfields-method-record.md) to read the BLOB into memory and calculate it. Then you can use the BLOB in AL code or display it in the application.  

 It is not supported to insert a BLOB field into a Variant.  

 It is not supported for a page to access a BLOB field from a table other than the SourceTable of the page.  

-->

## See Also
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  