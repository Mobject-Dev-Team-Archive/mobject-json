# Changelog

## 0.3.0 

- Added TryLocate() method which attempts to resolve the path into an SJsonValue which can be used with the parser. 

## 0.2.0

- Added TryWrite() method which attempts to write a value at the specified path within a JSON document. If the path does not exist, the method will attempt to create the necessary structure in the JSON document to accommodate the value. 

## 0.1.1

- Refactored Json Path Syntax Parsing to it's own class.  It's now possible to parse paths using an I_JsonPathVisitor.
  This will allow future expansion to allow for writing to json using the path. 

## 0.1.0

- Updated to 4024.47
- Updated to use mobject-converters 0.1.1
- Added TryModify(), this method will modify a value if it exists

## 0.0.0

- First alpha release
