# JsonDomParser Class

## Definition

|             |                                                                                                                                           |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Namespace   | mobject-json                                                                                                                              |
| Library     | mobject-json                                                                                                                              |
| Inheritance | [FB_JsonDynDomParser](https://infosys.beckhoff.com/english.php?content=../content/1033/tf6701_tc3_iot_communication_mqtt/8101725835.html) |
| Implements  | N/A                                                                                                                                       |

## Remarks

The JsonDomParser Class is an extension to the current TwinCAT implementation of FB_JsonDynDomParser. This class adds functionality such as the ability to read from the JSON document using [JSONPath Syntax](https://support.smartbear.com/alertsite/docs/monitors/api/endpoint/jsonpath.html).

## Example

```declaration
PROGRAM Main
VAR
  jsonParser : JsonDomParser;
  json : T_MAXSTRING := '{"level1" : {"level2" : {"level3" : {"level4" : 123, "myArray" : ["a","b","c"]}}}}';
  result : DINT;
  newString : STRING := "d";
  successful : BOOL;
END_VAR
```

```body
// first parse the document
jsonParser.ParseDocument(json);

// use the new "TryRead" method to read values using JSONPath Syntax
successful := jsonParser.TryRead('.level1.level2.level3.level4', result); 
// successful = true
// result := 123

successful := jsonParser.TryModify('.level1.level2.level3.myArray[2]', newString); 
json := jsonParser.GetDocument();
// successful = true
// json = '{"level1" : {"level2" : {"level3" : {"level4" : 123, "myArray" : ["a","b","d"]}}}}';
```

## Methods

### TryModify()

Tries to modify the value at the path specified. The modify will fail if the path does not already exist.

#### Parameters

| Parameters | Datatype    | Description                                        |
| ---------- | ----------- | -------------------------------------------------- |
| Path       | T_MAXSTRING | The path of the value specified in JSONPath Syntax |
| Source     | ANY         | The symbol used as the source data                 |

#### Return

| Datatype | Description                               |
| -------- | ----------------------------------------- |
| BOOL     | Returns true if the modify was successful |

#### Usage

```example
// {"myInt" : 123}';
newValue := 456;
modified := jsonParser.TryModify('.myInt', newValue);  // {"myInt" : 456}, modified = true
```

### TryRead()

Tries to read the value at the path specified.

#### Parameters

| Parameters  | Datatype    | Description                                                  |
| ----------- | ----------- | ------------------------------------------------------------ |
| Path        | T_MAXSTRING | The path of the value specified in JSONPath Syntax           |
| Destination | ANY         | The symbol used as the destination if the read is successful |

#### Return

| Datatype | Description                             |
| -------- | --------------------------------------- |
| BOOL     | Returns true if the read was successful |

#### Usage

```example
// {"myInt" : 123}';
read := jsonParser.TryRead('.myInt',result);  // result = 123, read = true
```
