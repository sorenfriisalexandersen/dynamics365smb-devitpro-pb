---
title: "JsonValue Data Type"
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
# JsonValue Data Type
Is a container for any well-formed fundamental JSON value. A default JsonValue is set to the JSON value of NULL.



The following methods are available on instances of the JsonValue data type.

|Method name|Description|
|-----------|-----------|
|[Path()](jsonvalue-path-method.md)|Retrieves the JSON path of the value relative to its containing tree.|
|[ReadFrom(String)](jsonvalue-readfrom-string-method.md)|Reads the JSON data into a JsonValue variable.|
|[ReadFrom(InStream)](jsonvalue-readfrom-instream-method.md)|Reads the JSON data from the stream into a JsonValue variable.|
|[WriteTo(var Text)](jsonvalue-writeto-text-method.md)|Serializes and writes the JSON data of the JsonValue to a given object.|
|[WriteTo(OutStream)](jsonvalue-writeto-outstream-method.md)|Serializes and writes the JSON data of the JsonValue to a given object.|
|[SelectToken(String, var JsonToken)](jsonvalue-selecttoken-method.md)|Selects a JsonToken using a JPath expression.|
|[Clone()](jsonvalue-clone-method.md)|Creates a deep-copy of the JsonToken value.|
|[AsToken()](jsonvalue-astoken-method.md)|Converts the value in a JsonValue to a JsonToken data type.|
|[IsNull()](jsonvalue-isnull-method.md)|Indicates whether the JsonValue contains the JSON value of NULL.|
|[IsUndefined()](jsonvalue-isundefined-method.md)|Indicates whether the JsonValue contains the JSON value of UNDEFINED.|
|[AsBoolean()](jsonvalue-asboolean-method.md)|Converts the value in a JsonValue to a Boolean data type.|
|[AsChar()](jsonvalue-aschar-method.md)|Converts the value in a JsonValue to a Char data type.|
|[AsByte()](jsonvalue-asbyte-method.md)|Converts the value in a JsonValue to a Byte data type.|
|[AsOption()](jsonvalue-asoption-method.md)|Converts the value in a JsonValue to an Option data type.|
|[AsInteger()](jsonvalue-asinteger-method.md)|Converts the value in a JsonValue to an Integer data type.|
|[AsBigInteger()](jsonvalue-asbiginteger-method.md)|Converts the value in a JsonValue to an BigInteger data type.|
|[AsDecimal()](jsonvalue-asdecimal-method.md)|Converts the value in a JsonValue to a Decimal data type.|
|[AsDuration()](jsonvalue-asduration-method.md)|Converts the value in a JsonValue to a Duration data type.|
|[AsDate()](jsonvalue-asdate-method.md)|Converts the value in a JsonValue to a Date data type.|
|[AsTime()](jsonvalue-astime-method.md)|Converts the value in a JsonValue to a Time data type.|
|[AsDateTime()](jsonvalue-asdatetime-method.md)|Converts the value in a JsonValue to a DateTime data type.|
|[AsText()](jsonvalue-astext-method.md)|Converts the value in a JsonValue to a Text data type.|
|[AsCode()](jsonvalue-ascode-method.md)|Converts the value in a JsonValue to a Code data type.|
|[SetValue(Boolean)](jsonvalue-setvalue-boolean-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(Char)](jsonvalue-setvalue-char-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(Byte)](jsonvalue-setvalue-byte-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(Option)](jsonvalue-setvalue-option-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(Integer)](jsonvalue-setvalue-integer-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(BigInteger)](jsonvalue-setvalue-biginteger-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(Decimal)](jsonvalue-setvalue-decimal-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(Duration)](jsonvalue-setvalue-duration-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(Date)](jsonvalue-setvalue-date-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(Time)](jsonvalue-setvalue-time-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(DateTime)](jsonvalue-setvalue-datetime-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValue(String)](jsonvalue-setvalue-string-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given value.|
|[SetValueToNull()](jsonvalue-setvaluetonull-method.md)|Set the contents of the JsonValue variable to the JSON representation of NULL.|
|[SetValueToUndefined()](jsonvalue-setvaluetoundefined-method.md)|Set the contents of the JsonValue variable to the JSON representation of UNDEFINED.|

[//]: # (IMPORTANT: END>DO_NOT_EDIT)

> [!NOTE]  
> For performance reasons all HTTP, JSON, TextBuilder, and XML types are reference types, not value types. Reference types holds a pointer to the data elsewhere in memory, whereas value types store its own data.

## See Also
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)  