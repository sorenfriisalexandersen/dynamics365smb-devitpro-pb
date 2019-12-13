---
title: "Xmlport Data Type"
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
# Xmlport Data Type
XmlPorts are used to export or import data between an external source and a Microsoft Dynamics Business Central database.


The following methods are available on the Xmlport data type.


|Method name|Description|
|-----------|-----------|
|[Import(Integer, var InStream [, var Record])](xmlport-import-method.md)|Reads and parses an incoming XML data stream (XML document).|
|[Export(Integer, var OutStream [, var Record])](xmlport-export-method.md)|Creates an XML data stream (XML document) and sends it to a chosen destination.|
|[Run(Integer [, Boolean] [, Boolean] [, var Record])](xmlport-run-method.md)|Loads and executes the XmlPort that you specify.|

The following methods are available on instances of the Xmlport data type.

|Method name|Description|
|-----------|-----------|
|[CurrentPath()](xmlportinstance-currentpath-method.md)|Returns the CurrentPath for a given node, used when exporting an XmlPort.|
|[Export()](xmlportinstance-export-method.md)|Creates an XML data stream (XML document) and sends it to a chosen destination.|
|[Import()](xmlportinstance-import-method.md)|Reads and parses an incoming XML data stream (XML document).|
|[Run()](xmlportinstance-run-method.md)|Loads and executes the XmlPort that you specify.|
|[FieldDelimiter([String])](xmlportinstance-fielddelimiter-method.md)|Gets and sets the FiledDelimiter used when running, importing or exporting the XmlPort.|
|[FieldSeparator([String])](xmlportinstance-fieldseparator-method.md)|Gets and sets the FieldSeparator used when running, importing or exporting the XmlPort.|
|[RecordSeparator([String])](xmlportinstance-recordseparator-method.md)|Gets and sets the RecordSeparator used when running, importing or exporting the XmlPort.|
|[TableSeparator([String])](xmlportinstance-tableseparator-method.md)|Gets and sets the TableSeparator used when running, importing or exporting the XmlPort.|
|[Filename([String])](xmlportinstance-filename-method.md)|Gets the current value of the FileName Property of an XmlPort and sets this property to a new value.|
|[TextEncoding([TextEncoding])](xmlportinstance-textencoding-method.md)|Gets and sets the TextEncoding used when running, importing or exporting the XmlPort.|
|[SetSource(var InStream)](xmlportinstance-setsource-method.md)|Sets the source InStream of the XmlPort.|
|[SetDestination(var OutStream)](xmlportinstance-setdestination-method.md)|Sets the destination OutStream of the XmlPort.|
|[ImportFile([Boolean])](xmlportinstance-importfile-method.md)|Gets or sets the ImportFile property.|
|[SetTableView(var Record)](xmlportinstance-settableview-method.md)|Applies the table view on the current record as the table view for the page, report, or XmlPort.|
|[Break()](xmlportinstance-break-method.md)|Exits from a loop or a trigger in a data item trigger of a report or XmlPort.|
|[BreakUnbound()](xmlportinstance-breakunbound-method.md)|Exits from a loop on records in an XmlPort trigger.|
|[Skip()](xmlportinstance-skip-method.md)|Skips the current iteration of the current report or XmlPort.|
|[Quit()](xmlportinstance-quit-method.md)|Aborts the processing of a report or XmlPort.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)
## See Also  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  
[XMLport Overview](../../devenv-xmlport-overview.md)
