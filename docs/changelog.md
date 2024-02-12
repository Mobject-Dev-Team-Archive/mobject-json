# Changelog

## v1.2.0-beta

- Updated to support mobject-serialization v0.3.0-alpha.
- Added JsonSeralizer.AddObject
- Added JsonSeralizer.AddKeyObject
- Added JsonDeserializer + tests

!> This update contains the following breaking changes.

- JsonSeralizer.AddKeyRawObject renamed to .AddKeyRawJson
- JsonSeralizer.AddRawObject renamed to AddRawJson

## v1.1.0-beta

- Updated to support mobject-serialization v0.1.0-alpha.
- Added JsonSerializer

## v1.0.1-beta

- Updated to support mobject-converters v1.0.1-beta.
- Bugfix with JsonDomParser writing Int and Uint64.
- Added explicit conversion to remove warning message.

## v1.0.0-beta

- Changed status from alpha to beta.
- Updated documentation to support dark mode.
- Library built using 4024.53.
- Updated to support mobject-disposable v1.0.0-beta.
- Updated to support mobject-converters v1.0.0-beta.

## v0.3.0-alpha

- Added TryLocate() method which attempts to resolve the path into an SJsonValue which can be used with the parser.

## v0.2.0-alpha

- Added TryWrite() method which attempts to write a value at the specified path within a JSON document. If the path does not exist, the method will attempt to create the necessary structure in the JSON document to accommodate the value.

## v0.1.1-alpha

- Refactored Json Path Syntax Parsing to it's own class. It's now possible to parse paths using an I_JsonPathVisitor.
  This will allow future expansion to allow for writing to json using the path.

## v0.1.0-alpha

- Updated to 4024.47
- Updated to use mobject-converters 0.1.1
- Added TryModify(), this method will modify a value if it exists

## v0.0.0-alpha

- First alpha release
