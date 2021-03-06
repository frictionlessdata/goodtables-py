---
title: API Reference
---

## AnyType

```python
class AnyType(Type)
```

Any type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## ApiServer

```python
class ApiServer(Server)
```

API server implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.server import ApiParser`

## ArrayType

```python
class ArrayType(Type)
```

Array type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## BigqueryDialect

```python
class BigqueryDialect(Dialect)
```

Bigquery dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.bigquery import BigqueryDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `project` _str_ - project
- `dataset?` _str_ - dataset
- `table?` _str_ - table
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## BigqueryParser

```python
class BigqueryParser(Parser)
```

Bigquery parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.bigquery import BigqueryParser`

## BigqueryPlugin

```python
class BigqueryPlugin(Plugin)
```

Plugin for BigQuery

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.bigquery import BigqueryPlugin`

## BigqueryStorage

```python
class BigqueryStorage(Storage)
```

BigQuery storage implementation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.bigquery import BigqueryStorage`

**Arguments**:

- `service` _object_ - BigQuery `Service` object
- `project` _str_ - BigQuery project name
- `dataset` _str_ - BigQuery dataset name
- `prefix?` _str_ - prefix for all names

## BooleanType

```python
class BooleanType(Type)
```

Boolean type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## CellError

```python
class CellError(RowError)
```

Cell error representation

**Arguments**:

- `descriptor?` _str|dict_ - error descriptor
- `note` _str_ - an error note
- `cells` _str[]_ - row cells
- `row_number` _int_ - row number
- `row_position` _int_ - row position
- `cell` _str_ - errored cell
- `field_name` _str_ - field name
- `field_number` _int_ - field number
- `field_position` _int_ - field position
  
  # Raises
- `FrictionlessException` - raise any error that occurs during the process

### cellError.from\_row

```python
 | @classmethod
 | from_row(cls, row, *, note, field_name)
```

Create and error from a cell

**Arguments**:

- `row` _Row_ - row
- `note` _str_ - note
- `field_name` _str_ - field name
  

**Returns**:

- `CellError` - error

## Check

```python
class Check(Metadata)
```

Check representation.

API      | Usage
-------- | --------
Public   | `from frictionless import Checks`

It's an interface for writing Frictionless checks.

**Arguments**:

- `descriptor?` _str|dict_ - schema descriptor
  

**Raises**:

- `FrictionlessException` - raise if metadata is invalid

### check.resource

```python
 | @property
 | resource()
```

**Returns**:

- `Resource?` - resource object available after the `check.connect` call

### check.connect

```python
 | connect(resource)
```

Connect to the given resource

**Arguments**:

- `resource` _Resource_ - data resource

### check.prepare

```python
 | prepare()
```

Called before validation

### check.validate\_check

```python
 | validate_check()
```

Called to validate the check itself

**Yields**:

- `Error` - found errors

### check.validate\_source

```python
 | validate_source()
```

Called to validate the given source

**Yields**:

- `Error` - found errors

### check.validate\_schema

```python
 | validate_schema()
```

Called to validate the given schema

**Arguments**:

- `schema` _Schema_ - table schema
  

**Yields**:

- `Error` - found errors

### check.validate\_header

```python
 | validate_header()
```

Called to validate the given header

**Arguments**:

- `header` _Header_ - table header
  

**Yields**:

- `Error` - found errors

### check.validate\_row

```python
 | validate_row(row)
```

Called to validate the given row (on every row)

**Arguments**:

- `row` _Row_ - table row
  

**Yields**:

- `Error` - found errors

### check.validate\_table

```python
 | validate_table()
```

Called to validate the table (after no rows left)

**Yields**:

- `Error` - found errors

## CkanDialect

```python
class CkanDialect(Dialect)
```

Ckan dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.ckan import CkanDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `resource?` _str_ - resource
- `dataset?` _str_ - dataset
- `apikey?` _str_ - apikey
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## CkanParser

```python
class CkanParser(Parser)
```

Ckan parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.ckan import CkanParser`

## CkanPlugin

```python
class CkanPlugin(Plugin)
```

Plugin for CKAN

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.ckan import CkanPlugin`

## CkanStorage

```python
class CkanStorage(Storage)
```

Ckan storage implementation

**Arguments**:

- `url` _string_ - CKAN instance url e.g. "https://demo.ckan.org"
- `dataset` _string_ - dataset id in CKAN e.g. "my-dataset"
- `apikey?` _str_ - API key for CKAN e.g. "51912f57-a657-4caa-b2a7-0a1c16821f4b"
  
  
  API      | Usage
  -------- | --------
  Public   | `from frictionless.plugins.ckan import CkanStorage`

## Control

```python
class Control(Metadata)
```

Control representation

API      | Usage
-------- | --------
Public   | `from frictionless import Control`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## CsvDialect

```python
class CsvDialect(Dialect)
```

Csv dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.csv import CsvDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `delimiter?` _str_ - csv delimiter
- `line_terminator?` _str_ - csv line terminator
- `quote_char?` _str_ - csv quote char
- `double_quote?` _bool_ - csv double quote
- `escape_char?` _str_ - csv escape char
- `null_sequence?` _str_ - csv null sequence
- `skip_initial_space?` _bool_ - csv skip initial space
- `comment_char?` _str_ - csv comment char
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### csvDialect.delimiter

```python
 | @Metadata.property
 | delimiter()
```

**Returns**:

- `str` - delimiter

### csvDialect.line\_terminator

```python
 | @Metadata.property
 | line_terminator()
```

**Returns**:

- `str` - line terminator

### csvDialect.quote\_char

```python
 | @Metadata.property
 | quote_char()
```

**Returns**:

- `str` - quote char

### csvDialect.double\_quote

```python
 | @Metadata.property
 | double_quote()
```

**Returns**:

- `bool` - double quote

### csvDialect.escape\_char

```python
 | @Metadata.property
 | escape_char()
```

**Returns**:

- `str?` - escape char

### csvDialect.null\_sequence

```python
 | @Metadata.property
 | null_sequence()
```

**Returns**:

- `str?` - null sequence

### csvDialect.skip\_initial\_space

```python
 | @Metadata.property
 | skip_initial_space()
```

**Returns**:

- `bool` - if skipping initial space

### csvDialect.comment\_char

```python
 | @Metadata.property
 | comment_char()
```

**Returns**:

- `str?` - comment char

### csvDialect.expand

```python
 | expand()
```

Expand metadata

### csvDialect.to\_python

```python
 | to_python()
```

Conver to Python's `csv.Dialect`

## CsvParser

```python
class CsvParser(Parser)
```

CSV parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.csv import CsvPlugins

## CsvPlugin

```python
class CsvPlugin(Plugin)
```

Plugin for Pandas

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.csv import CsvPlugin`

## DateType

```python
class DateType(Type)
```

Date type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## DatetimeType

```python
class DatetimeType(Type)
```

Datetime type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## Detector

```python
class Detector()
```

Detector representation

API      | Usage
-------- | --------
Public   | `from frictionless import Detector`

**Arguments**:

  
- `buffer_size?` _int_ - The amount of bytes to be extracted as a buffer.
  It defaults to 10000
  
- `sample_size?` _int_ - The amount of rows to be extracted as a samle.
  It defaults to 100
  
- `field_type?` _str_ - Enforce all the inferred types to be this type.
  For more information, please check "Describing  Data" guide.
  
- `field_names?` _str[]_ - Enforce all the inferred fields to have provided names.
  For more information, please check "Describing  Data" guide.
  
- `field_confidence?` _float_ - A number from 0 to 1 setting the infer confidence.
  If  1 the data is guaranteed to be valid against the inferred schema.
  For more information, please check "Describing  Data" guide.
  It defaults to 0.9
  
- `field_float_numbers?` _bool_ - Flag to indicate desired number type.
  By default numbers will be `Decimal`; if `True` - `float`.
  For more information, please check "Describing  Data" guide.
  It defaults to `False`
  
- `field_missing_values?` _str[]_ - String to be considered as missing values.
  For more information, please check "Describing  Data" guide.
  It defaults to `['']`
  
- `schema_sync?` _bool_ - Whether to sync the schema.
  If it sets to `True` the provided schema will be mapped to
  the inferred schema. It means that, for example, you can
  provide a subset of fileds to be applied on top of the inferred
  fields or the provided schema can have different order of fields.
  
- `schema_patch?` _dict_ - A dictionary to be used as an inferred schema patch.
  The form of this dictionary should follow the Schema descriptor form
  except for the `fields` property which should be a mapping with the
  key named after a field name and the values being a field patch.
  For more information, please check "Extracting Data" guide.

### detector.detect\_encoding

```python
 | detect_encoding(sample)
```

Detect encoding from sample

**Arguments**:

- `sample` _byte_ - byte sample
  

**Returns**:

- `str` - encoding

### detector.detect\_layout

```python
 | detect_layout(sample)
```

Detect layout from sample

**Arguments**:

- `sample` _any[][]_ - data sample
  

**Returns**:

- `Layout` - layout

### detector.detect\_schema

```python
 | detect_schema(sample, *, labels=None, schema=None)
```

Detect schema from sample

**Arguments**:

- `sample` _any[][]_ - data sample
- `labels?` _str[]_ - data labels
- `schema?` _Schema_ - data schema
  

**Returns**:

- `Schema` - schema

## Dialect

```python
class Dialect(Metadata)
```

Dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless import Dialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## DurationType

```python
class DurationType(Type)
```

Duration type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## Error

```python
class Error(Metadata)
```

Error representation

API      | Usage
-------- | --------
Public   | `from frictionless import errors`

**Arguments**:

- `descriptor?` _str|dict_ - error descriptor
- `note` _str_ - an error note
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### error.note

```python
 | @property
 | note()
```

**Returns**:

- `str` - note

### error.message

```python
 | @property
 | message()
```

**Returns**:

- `str` - message

## ExcelDialect

```python
class ExcelDialect(Dialect)
```

Excel dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.excel import ExcelDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `sheet?` _int|str_ - number from 1 or name of an excel sheet
- `workbook_cache?` _dict_ - workbook cache
- `fill_merged_cells?` _bool_ - whether to fill merged cells
- `preserve_formatting?` _bool_ - whither to preserve formatting
- `adjust_floating_point_error?` _bool_ - whether to adjust floating point error
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### excelDialect.sheet

```python
 | @Metadata.property
 | sheet()
```

**Returns**:

- `str|int` - sheet

### excelDialect.workbook\_cache

```python
 | @Metadata.property
 | workbook_cache()
```

**Returns**:

- `dict` - workbook cache

### excelDialect.fill\_merged\_cells

```python
 | @Metadata.property
 | fill_merged_cells()
```

**Returns**:

- `bool` - fill merged cells

### excelDialect.preserve\_formatting

```python
 | @Metadata.property
 | preserve_formatting()
```

**Returns**:

- `bool` - preserve formatting

### excelDialect.adjust\_floating\_point\_error

```python
 | @Metadata.property
 | adjust_floating_point_error()
```

**Returns**:

- `bool` - adjust floating point error

### excelDialect.expand

```python
 | expand()
```

Expand metadata

## ExcelPlugin

```python
class ExcelPlugin(Plugin)
```

Plugin for Excel

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.excel import ExcelPlugin`

## Field

```python
class Field(Metadata)
```

Field representation

API      | Usage
-------- | --------
Public   | `from frictionless import Field`

**Arguments**:

- `descriptor?` _str|dict_ - field descriptor
- `name?` _str_ - field name (for machines)
- `title?` _str_ - field title (for humans)
- `descriptor?` _str_ - field descriptor
- `type?` _str_ - field type e.g. `string`
- `format?` _str_ - field format e.g. `default`
- `missing_values?` _str[]_ - missing values
- `constraints?` _dict_ - constraints
- `rdf_type?` _str_ - RDF type
- `schema?` _Schema_ - parent schema object
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### field.name

```python
 | @Metadata.property
 | name()
```

**Returns**:

- `str` - name

### field.title

```python
 | @Metadata.property
 | title()
```

**Returns**:

- `str?` - title

### field.description

```python
 | @Metadata.property
 | description()
```

**Returns**:

- `str?` - description

### field.type

```python
 | @Metadata.property
 | type()
```

**Returns**:

- `str` - type

### field.format

```python
 | @Metadata.property
 | format()
```

**Returns**:

- `str` - format

### field.missing\_values

```python
 | @Metadata.property
 | missing_values()
```

**Returns**:

- `str[]` - missing values

### field.constraints

```python
 | @Metadata.property
 | constraints()
```

**Returns**:

- `dict` - constraints

### field.rdf\_type

```python
 | @Metadata.property
 | rdf_type()
```

**Returns**:

- `str?` - RDF Type

### field.required

```python
 | @Metadata.property(
 |         write=lambda self, value: setitem(self.constraints, "required", value)
 |     )
 | required()
```

**Returns**:

- `bool` - if field is requried

### field.schema

```python
 | @property
 | schema()
```

**Returns**:

- `Schema?` - parent schema

### field.true\_values

```python
 | @Metadata.property
 | true_values()
```

**Returns**:

- `str[]` - true values

### field.false\_values

```python
 | @Metadata.property
 | false_values()
```

**Returns**:

- `str[]` - false values

### field.bare\_number

```python
 | @Metadata.property
 | bare_number()
```

**Returns**:

- `bool` - if a bare number

### field.float\_number

```python
 | @Metadata.property
 | float_number()
```

**Returns**:

- `bool` - whether it's a floating point number

### field.decimal\_char

```python
 | @Metadata.property
 | decimal_char()
```

**Returns**:

- `str` - decimal char

### field.group\_char

```python
 | @Metadata.property
 | group_char()
```

**Returns**:

- `str` - group char

### field.expand

```python
 | expand()
```

Expand metadata

### field.read\_cell

```python
 | read_cell(cell)
```

Read cell

**Arguments**:

- `cell` _any_ - cell
  

**Returns**:

  (any, OrderedDict): processed cell and dict of notes

### field.read\_cell\_convert

```python
 | read_cell_convert(cell)
```

Read cell (convert only)

**Arguments**:

- `cell` _any_ - cell
  

**Returns**:

- `any/None` - processed cell or None if an error

### field.read\_cell\_checks

```python
 | @Metadata.property(write=False)
 | read_cell_checks()
```

Read cell (checks only)

**Returns**:

- `OrderedDict` - dictionlary of check function by a constraint name

### field.write\_cell

```python
 | write_cell(cell, *, ignore_missing=False)
```

Write cell

**Arguments**:

- `cell` _any_ - cell to convert
- `ignore_missing?` _bool_ - don't convert None values
  

**Returns**:

  (any, OrderedDict): processed cell and dict of notes

### field.write\_cell\_convert

```python
 | write_cell_convert(cell)
```

Write cell (convert only)

**Arguments**:

- `cell` _any_ - cell
  

**Returns**:

- `any/None` - processed cell or None if an error

### field.write\_cell\_missing\_value

```python
 | @Metadata.property(write=False)
 | write_cell_missing_value()
```

Write cell (missing value only)

**Returns**:

- `str` - a value to replace None cells

## File

```python
class File()
```

File representation

## FilelikeControl

```python
class FilelikeControl(Control)
```

Filelike control representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.filelike import FilelikeControl`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## FilelikeLoader

```python
class FilelikeLoader(Loader)
```

Filelike loader implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.filelike import FilelikeLoader`

## FilelikePlugin

```python
class FilelikePlugin(Plugin)
```

Plugin for Local Data

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.filelike import FilelikePlugin`

## FrictionlessException

```python
class FrictionlessException(Exception)
```

Main Frictionless exception

API      | Usage
-------- | --------
Public   | `from frictionless import FrictionlessException`

**Arguments**:

- `error` _Error_ - an underlaying error

### frictionlessException.error

```python
 | @property
 | error()
```

**Returns**:

- `Error` - error

## GeojsonType

```python
class GeojsonType(Type)
```

Geojson type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## GeopointType

```python
class GeopointType(Type)
```

Geopoint type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## GsheetsDialect

```python
class GsheetsDialect(Dialect)
```

Gsheets dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.gsheets import GsheetsDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### gsheetsDialect.credentials

```python
 | @Metadata.property
 | credentials()
```

**Returns**:

- `str` - credentials

## GsheetsParser

```python
class GsheetsParser(Parser)
```

Google Sheets parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.gsheets import GsheetsParser`

## GsheetsPlugin

```python
class GsheetsPlugin(Plugin)
```

Plugin for Google Sheets

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.gsheets import GsheetsPlugin`

## Header

```python
class Header(list)
```

Header representation

API      | Usage
-------- | --------
Public   | `from frictionless import Header`

> Constructor of this object is not Public API

**Arguments**:

- `labels` _any[]_ - header row labels
- `fields` _Field[]_ - table fields
- `field_positions` _int[]_ - field positions
- `row_positions` _int[]_ - row positions
- `ignore_case` _bool_ - ignore case

### header.labels

```python
 | @cached_property
 | labels()
```

**Returns**:

- `Schema` - table labels

### header.fields

```python
 | @cached_property
 | fields()
```

**Returns**:

- `Schema` - table fields

### header.field\_names

```python
 | @cached_property
 | field_names()
```

**Returns**:

- `str[]` - table field names

### header.field\_positions

```python
 | @cached_property
 | field_positions()
```

**Returns**:

- `int[]` - table field positions

### header.row\_positions

```python
 | @cached_property
 | row_positions()
```

**Returns**:

- `int[]` - table row positions

### header.missing

```python
 | @cached_property
 | missing()
```

**Returns**:

- `bool` - if there is not header

### header.errors

```python
 | @cached_property
 | errors()
```

**Returns**:

- `Error[]` - header errors

### header.valid

```python
 | @cached_property
 | valid()
```

**Returns**:

- `bool` - if header valid

### header.to\_str

```python
 | to_str()
```

**Returns**:

- `str` - a row as a CSV string

### header.to\_list

```python
 | to_list()
```

Convert to a list

## HeaderError

```python
class HeaderError(TableError)
```

Header error representation

**Arguments**:

- `descriptor?` _str|dict_ - error descriptor
- `note` _str_ - an error note
- `labels` _str[]_ - header labels
- `label` _str_ - an errored label
- `field_name` _str_ - field name
- `field_number` _int_ - field number
- `field_position` _int_ - field position
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## HtmlDialect

```python
class HtmlDialect(Dialect)
```

Html dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.html import HtmlDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `selector?` _str_ - HTML selector
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### htmlDialect.selector

```python
 | @Metadata.property
 | selector()
```

**Returns**:

- `str` - selector

### htmlDialect.expand

```python
 | expand()
```

Expand metadata

## HtmlParser

```python
class HtmlParser(Parser)
```

HTML parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.html import HtmlParser`

## HtmlPlugin

```python
class HtmlPlugin(Plugin)
```

Plugin for HTML

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.html import HtmlPlugin`

## InlineDialect

```python
class InlineDialect(Dialect)
```

Inline dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.inline import InlineDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `keys?` _str[]_ - a list of strings to use as data keys
- `keyed?` _bool_ - whether data rows are keyed
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### inlineDialect.keys

```python
 | @Metadata.property
 | keys()
```

**Returns**:

- `str[]?` - keys

### inlineDialect.keyed

```python
 | @Metadata.property
 | keyed()
```

**Returns**:

- `bool` - keyed

### inlineDialect.expand

```python
 | expand()
```

Expand metadata

## InlineParser

```python
class InlineParser(Parser)
```

Inline parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.inline import InlineParser

## InlinePlugin

```python
class InlinePlugin(Plugin)
```

Plugin for Inline

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.inline import InlinePlugin`

## Inquiry

```python
class Inquiry(Metadata)
```

Inquiry representation.

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### inquiry.tasks

```python
 | @property
 | tasks()
```

**Returns**:

- `dict[]` - tasks

## InquiryTask

```python
class InquiryTask(Metadata)
```

Inquiry task representation.

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### inquiryTask.source

```python
 | @property
 | source()
```

**Returns**:

- `any` - source

### inquiryTask.type

```python
 | @property
 | type()
```

**Returns**:

- `string?` - type

## IntegerType

```python
class IntegerType(Type)
```

Integer type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## JsonDialect

```python
class JsonDialect(Dialect)
```

Json dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.json import JsonDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `keys?` _str[]_ - a list of strings to use as data keys
- `keyed?` _bool_ - whether data rows are keyed
- `property?` _str_ - a path within JSON to the data
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### jsonDialect.keys

```python
 | @Metadata.property
 | keys()
```

**Returns**:

- `str[]?` - keys

### jsonDialect.keyed

```python
 | @Metadata.property
 | keyed()
```

**Returns**:

- `bool` - keyed

### jsonDialect.property

```python
 | @Metadata.property
 | property()
```

**Returns**:

- `str?` - property

### jsonDialect.expand

```python
 | expand()
```

Expand metadata

## JsonParser

```python
class JsonParser(Parser)
```

JSON parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.json import JsonParser

## JsonPlugin

```python
class JsonPlugin(Plugin)
```

Plugin for Json

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.json import JsonPlugin`

## JsonlParser

```python
class JsonlParser(Parser)
```

JSONL parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.json import JsonlParser

## LabelError

```python
class LabelError(HeaderError)
```

Label error representation

**Arguments**:

- `descriptor?` _str|dict_ - error descriptor
- `note` _str_ - an error note
- `labels` _str[]_ - header labels
- `label` _str_ - an errored label
- `field_name` _str_ - field name
- `field_number` _int_ - field number
- `field_position` _int_ - field position
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## Layout

```python
class Layout(Metadata)
```

Layout representation

API      | Usage
-------- | --------
Public   | `from frictionless import Layout`

**Arguments**:

- `descriptor?` _str|dict_ - layout descriptor
  pick_fields? ((str|int)[]): what fields to pick
  skip_fields? ((str|int)[]): what fields to skip
- `limit_fields?` _int_ - amount of fields
- `offset_fields?` _int_ - from what field to start
  pick_rows? ((str|int)[]): what rows to pick
  skip_rows? ((str|int)[]): what rows to skip
- `limit_rows?` _int_ - amount of rows
- `offset_rows?` _int_ - from what row to start

### layout.header

```python
 | @Metadata.property
 | header()
```

**Returns**:

- `bool` - if there is a header row

### layout.header\_rows

```python
 | @Metadata.property
 | header_rows()
```

**Returns**:

- `int[]` - header rows

### layout.header\_join

```python
 | @Metadata.property
 | header_join()
```

**Returns**:

- `str` - header joiner

### layout.header\_case

```python
 | @Metadata.property
 | header_case()
```

**Returns**:

- `str` - header case sensitive

### layout.pick\_fields

```python
 | @Metadata.property
 | pick_fields()
```

**Returns**:

- `(str|int)[]?` - pick fields

### layout.skip\_fields

```python
 | @Metadata.property
 | skip_fields()
```

**Returns**:

- `(str|int)[]?` - skip fields

### layout.limit\_fields

```python
 | @Metadata.property
 | limit_fields()
```

**Returns**:

- `int?` - limit fields

### layout.offset\_fields

```python
 | @Metadata.property
 | offset_fields()
```

**Returns**:

- `int?` - offset fields

### layout.pick\_rows

```python
 | @Metadata.property
 | pick_rows()
```

**Returns**:

- `(str|int)[]?` - pick rows

### layout.skip\_rows

```python
 | @Metadata.property
 | skip_rows()
```

**Returns**:

- `(str|int)[]?` - skip rows

### layout.limit\_rows

```python
 | @Metadata.property
 | limit_rows()
```

**Returns**:

- `int?` - limit rows

### layout.offset\_rows

```python
 | @Metadata.property
 | offset_rows()
```

**Returns**:

- `int?` - offset rows

### layout.is\_field\_filtering

```python
 | @Metadata.property(write=False)
 | is_field_filtering()
```

**Returns**:

- `bool` - whether there is a field filtering

### layout.pick\_fields\_compiled

```python
 | @Metadata.property(write=False)
 | pick_fields_compiled()
```

**Returns**:

- `re?` - compiled pick fields

### layout.skip\_fields\_compiled

```python
 | @Metadata.property(write=False)
 | skip_fields_compiled()
```

**Returns**:

- `re?` - compiled skip fields

### layout.pick\_rows\_compiled

```python
 | @Metadata.property(write=False)
 | pick_rows_compiled()
```

**Returns**:

- `re?` - compiled pick rows

### layout.skip\_rows\_compiled

```python
 | @Metadata.property(write=False)
 | skip_rows_compiled()
```

**Returns**:

- `re?` - compiled skip fields

### layout.expand

```python
 | expand()
```

Expand metadata

## Loader

```python
class Loader()
```

Loader representation

API      | Usage
-------- | --------
Public   | `from frictionless import Loader`

**Arguments**:

- `resource` _Resource_ - resource

### loader.resource

```python
 | @property
 | resource()
```

**Returns**:

- `resource` _Resource_ - resource

### loader.byte\_stream

```python
 | @property
 | byte_stream()
```

Resource byte stream

The stream is available after opening the loader

**Returns**:

- `io.ByteStream` - resource byte stream

### loader.text\_stream

```python
 | @property
 | text_stream()
```

Resource text stream

The stream is available after opening the loader

**Returns**:

- `io.TextStream` - resource text stream

### loader.open

```python
 | open()
```

Open the loader as "io.open" does

### loader.close

```python
 | close()
```

Close the loader as "filelike.close" does

### loader.closed

```python
 | @property
 | closed()
```

Whether the loader is closed

**Returns**:

- `bool` - if closed

### loader.read\_byte\_stream

```python
 | read_byte_stream()
```

Read bytes stream

**Returns**:

- `io.ByteStream` - resource byte stream

### loader.read\_byte\_stream\_create

```python
 | read_byte_stream_create()
```

Create bytes stream

**Returns**:

- `io.ByteStream` - resource byte stream

### loader.read\_byte\_stream\_infer\_stats

```python
 | read_byte_stream_infer_stats(byte_stream)
```

Infer byte stream stats

**Arguments**:

- `byte_stream` _io.ByteStream_ - resource byte stream
  

**Returns**:

- `io.ByteStream` - resource byte stream

### loader.read\_byte\_stream\_decompress

```python
 | read_byte_stream_decompress(byte_stream)
```

Decompress byte stream

**Arguments**:

- `byte_stream` _io.ByteStream_ - resource byte stream
  

**Returns**:

- `io.ByteStream` - resource byte stream

### loader.read\_text\_stream

```python
 | read_text_stream()
```

Read text stream

**Returns**:

- `io.TextStream` - resource text stream

### loader.read\_text\_stream\_infer\_encoding

```python
 | read_text_stream_infer_encoding(byte_stream)
```

Infer text stream encoding

**Arguments**:

- `byte_stream` _io.ByteStream_ - resource byte stream

### loader.read\_text\_stream\_decode

```python
 | read_text_stream_decode(byte_stream)
```

Decode text stream

**Arguments**:

- `byte_stream` _io.ByteStream_ - resource byte stream
  

**Returns**:

- `text_stream` _io.TextStream_ - resource text stream

### loader.write\_byte\_stream

```python
 | write_byte_stream(path)
```

Write from a temporary file

**Arguments**:

- `path` _str_ - path to a temporary file
  

**Returns**:

- `any` - result of writing e.g. resulting path

### loader.write\_byte\_stream\_create

```python
 | write_byte_stream_create(path)
```

Create byte stream for writing

**Arguments**:

- `path` _str_ - path to a temporary file
  

**Returns**:

- `io.ByteStream` - byte stream

### loader.write\_byte\_stream\_save

```python
 | write_byte_stream_save(byte_stream)
```

Store byte stream

## LocalControl

```python
class LocalControl(Control)
```

Local control representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.local import LocalControl`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## LocalLoader

```python
class LocalLoader(Loader)
```

Local loader implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.local import LocalLoader`

## LocalPlugin

```python
class LocalPlugin(Plugin)
```

Plugin for Local Data

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.local import LocalPlugin`

## Metadata

```python
class Metadata(helpers.ControlledDict)
```

Metadata representation

API      | Usage
-------- | --------
Public   | `from frictionless import Metadata`

**Arguments**:

- `descriptor?` _str|dict_ - metadata descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### metadata.setinitial

```python
 | setinitial(key, value)
```

Set an initial item in a subclass' constructor

**Arguments**:

- `key` _str_ - key
- `value` _any_ - value

### metadata.to\_copy

```python
 | to_copy()
```

Create a copy of the metadata

**Returns**:

- `Metadata` - a copy of the metadata

### metadata.to\_dict

```python
 | to_dict()
```

Convert metadata to a dict

**Returns**:

- `dict` - metadata as a dict

### metadata.to\_json

```python
 | to_json(path=None, encoder_class=None)
```

Save metadata as a json

**Arguments**:

- `path` _str_ - target path
  

**Raises**:

- `FrictionlessException` - on any error

### metadata.to\_yaml

```python
 | to_yaml(path=None)
```

Save metadata as a yaml

**Arguments**:

- `path` _str_ - target path
  

**Raises**:

- `FrictionlessException` - on any error

### metadata.metadata\_valid

```python
 | @property
 | metadata_valid()
```

**Returns**:

- `bool` - whether the metadata is valid

### metadata.metadata\_errors

```python
 | @property
 | metadata_errors()
```

**Returns**:

- `Errors[]` - a list of the metadata errors

### metadata.metadata\_attach

```python
 | metadata_attach(name, value)
```

Helper method for attaching a value to  the metadata

**Arguments**:

- `name` _str_ - name
- `value` _any_ - value

### metadata.metadata\_extract

```python
 | metadata_extract(descriptor)
```

Helper method called during the metadata extraction

**Arguments**:

- `descriptor` _any_ - descriptor

### metadata.metadata\_process

```python
 | metadata_process()
```

Helper method called on any metadata change

### metadata.metadata\_validate

```python
 | metadata_validate(profile=None)
```

Helper method called on any metadata change

**Arguments**:

- `profile` _dict_ - a profile to validate against of

### metadata.property

```python
 | @staticmethod
 | property(func=None, *, cache=True, reset=True, write=True)
```

Create a metadata property

**Arguments**:

- `func` _func_ - method
- `cache?` _bool_ - cache
- `reset?` _bool_ - reset
- `write?` _func_ - write

## MultipartControl

```python
class MultipartControl(Control)
```

Multipart control representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.multipart import MultipartControl`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### multipartControl.expand

```python
 | expand()
```

Expand metadata

## MultipartLoader

```python
class MultipartLoader(Loader)
```

Multipart loader implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.multipart import MultipartLoader`

## MultipartPlugin

```python
class MultipartPlugin(Plugin)
```

Plugin for Multipart Data

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.multipart import MultipartPlugin`

## NumberType

```python
class NumberType(Type)
```

Number type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## ObjectType

```python
class ObjectType(Type)
```

Object type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## OdsDialect

```python
class OdsDialect(Dialect)
```

Ods dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.ods import OdsDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `sheet?` _str_ - sheet
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### odsDialect.sheet

```python
 | @Metadata.property
 | sheet()
```

**Returns**:

- `int|str` - sheet

### odsDialect.expand

```python
 | expand()
```

Expand metadata

## OdsParser

```python
class OdsParser(Parser)
```

ODS parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.ods import OdsParser`

## OdsPlugin

```python
class OdsPlugin(Plugin)
```

Plugin for ODS

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.ods import OdsPlugin`

## Package

```python
class Package(Metadata)
```

Package representation

API      | Usage
-------- | --------
Public   | `from frictionless import Package`

This class is one of the cornerstones of of Frictionless framework.
It manages underlaying resource and provides an ability to describe a package.


```python
package = Package(resources=[Resource(path="data/table.csv")])
package.get_resoure('table').read_rows() == [
    {'id': 1, 'name': 'english'},
    {'id': 2, 'name': '?????????'},
]
```

**Arguments**:

  
- `source` _any_ - Source of the package; can be in various forms.
  Usually, it's a package descriptor in a form of dict or path
  Also, it can be a glob pattern or a resource path
  
- `descriptor` _dict|str_ - A resource descriptor provided explicitly.
  Keyword arguments will patch this descriptor if provided.
  
- `resources?` _dict|Resource[]_ - A list of resource descriptors.
  It can be dicts or Resource instances.
  
- `id?` _str_ - A property reserved for globally unique identifiers.
  Examples of identifiers that are unique include UUIDs and DOIs.
  
- `name?` _str_ - A short url-usable (and preferably human-readable) name.
  This MUST be lower-case and contain only alphanumeric characters
  along with ???.???, ???_??? or ???-??? characters.
  
- `title?` _str_ - A Package title according to the specs
  It should a human-oriented title of the resource.
  
- `description?` _str_ - A Package description according to the specs
  It should a human-oriented description of the resource.
  
- `licenses?` _dict[]_ - The license(s) under which the package is provided.
  If omitted it's considered the same as the package's licenses.
  
- `sources?` _dict[]_ - The raw sources for this data package.
  It MUST be an array of Source objects.
  Each Source object MUST have a title and
  MAY have path and/or email properties.
  
- `profile?` _str_ - A string identifying the profile of this descriptor.
  For example, `fiscal-data-package`.
  
- `homepage?` _str_ - A URL for the home on the web that is related to this package.
  For example, github repository or ckan dataset address.
  
- `version?` _str_ - A version string identifying the version of the package.
  It should conform to the Semantic Versioning requirements and
  should follow the Data Package Version pattern.
  
- `contributors?` _dict[]_ - The people or organizations who contributed to this package.
  It MUST be an array. Each entry is a Contributor and MUST be an object.
  A Contributor MUST have a title property and MAY contain
  path, email, role and organization properties.
  
- `keywords?` _str[]_ - An Array of string keywords to assist users searching.
  For example, ['data', 'fiscal']
  
- `image?` _str_ - An image to use for this data package.
  For example, when showing the package in a listing.
  
- `created?` _str_ - The datetime on which this was created.
  The datetime must conform to the string formats for RFC3339 datetime,
  
- `basepath?` _str_ - A basepath of the resource
  The fullpath of the resource is joined `basepath` and /path`
  
- `detector?` _Detector_ - File/table detector.
  For more information, please check the Detector documentation.
  
- `onerror?` _ignore|warn|raise_ - Behaviour if there is an error.
  It defaults to 'ignore'. The default mode will ignore all errors
  on resource level and they should be handled by the user
  being available in Header and Row objects.
  
- `trusted?` _bool_ - Don't raise an exception on unsafe paths.
  A path provided as a part of the descriptor considered unsafe
  if there are path traversing or the path is absolute.
  A path provided as `source` or `path` is alway trusted.
  
- `hashing?` _str_ - a hashing algorithm for resources
  It defaults to 'md5'.
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### package.name

```python
 | @Metadata.property
 | name()
```

**Returns**:

- `str?` - package name

### package.id

```python
 | @Metadata.property
 | id()
```

**Returns**:

- `str?` - package id

### package.licenses

```python
 | @Metadata.property
 | licenses()
```

**Returns**:

- `dict?` - package licenses

### package.profile

```python
 | @Metadata.property
 | profile()
```

**Returns**:

- `str` - package profile

### package.title

```python
 | @Metadata.property
 | title()
```

**Returns**:

- `str?` - package title

### package.description

```python
 | @Metadata.property
 | description()
```

**Returns**:

- `str?` - package description

### package.homepage

```python
 | @Metadata.property
 | homepage()
```

**Returns**:

- `str?` - package homepage

### package.version

```python
 | @Metadata.property
 | version()
```

**Returns**:

- `str?` - package version

### package.sources

```python
 | @Metadata.property
 | sources()
```

**Returns**:

- `dict[]?` - package sources

### package.contributors

```python
 | @Metadata.property
 | contributors()
```

**Returns**:

- `dict[]?` - package contributors

### package.keywords

```python
 | @Metadata.property
 | keywords()
```

**Returns**:

- `str[]?` - package keywords

### package.image

```python
 | @Metadata.property
 | image()
```

**Returns**:

- `str?` - package image

### package.created

```python
 | @Metadata.property
 | created()
```

**Returns**:

- `str?` - package created

### package.hashing

```python
 | @Metadata.property(cache=False, write=False)
 | hashing()
```

**Returns**:

- `str` - package hashing

### package.basepath

```python
 | @Metadata.property(cache=False, write=False)
 | basepath()
```

**Returns**:

- `str` - package basepath

### package.onerror

```python
 | @Metadata.property(cache=False, write=False)
 | onerror()
```

**Returns**:

- `ignore|warn|raise` - on error bahaviour

### package.trusted

```python
 | @Metadata.property(cache=False, write=False)
 | trusted()
```

**Returns**:

- `str` - package trusted

### package.resources

```python
 | @Metadata.property
 | resources()
```

**Returns**:

- `Resources[]` - package resource

### package.resource\_names

```python
 | @Metadata.property(cache=False, write=False)
 | resource_names()
```

**Returns**:

- `str[]` - package resource names

### package.add\_resource

```python
 | add_resource(descriptor)
```

Add new resource to package.

**Arguments**:

- `descriptor` _dict_ - resource descriptor
  

**Returns**:

- `Resource/None` - added `Resource` instance or `None` if not added

### package.get\_resource

```python
 | get_resource(name)
```

Get resource by name.

**Arguments**:

- `name` _str_ - resource name
  

**Raises**:

- `FrictionlessException` - if resource is not found
  

**Returns**:

- `Resource/None` - `Resource` instance or `None` if not found

### package.has\_resource

```python
 | has_resource(name)
```

Check if a resource is present

**Arguments**:

- `name` _str_ - schema resource name
  

**Returns**:

- `bool` - whether there is the resource

### package.remove\_resource

```python
 | remove_resource(name)
```

Remove resource by name.

**Arguments**:

- `name` _str_ - resource name
  

**Raises**:

- `FrictionlessException` - if resource is not found
  

**Returns**:

- `Resource/None` - removed `Resource` instances or `None` if not found

### package.expand

```python
 | expand()
```

Expand metadata

It will add default values to the package.

### package.infer

```python
 | infer(*, stats=False)
```

Infer package's attributes

**Arguments**:

- `stats?` _bool_ - stream files completely and infer stats

### package.from\_zip

```python
 | @staticmethod
 | from_zip(path, **options)
```

Create a package from ZIP

### package.from\_storage

```python
 | @staticmethod
 | from_storage(storage)
```

Import package from storage

**Arguments**:

- `storage` _Storage_ - storage instance

### package.from\_ckan

```python
 | @staticmethod
 | from_ckan(*, url, dataset, apikey=None)
```

Import package from CKAN

**Arguments**:

- `url` _string_ - CKAN instance url e.g. "https://demo.ckan.org"
- `dataset` _string_ - dataset id in CKAN e.g. "my-dataset"
- `apikey?` _str_ - API key for CKAN e.g. "51912f57-a657-4caa-b2a7-0a1c16821f4b"

### package.from\_sql

```python
 | @staticmethod
 | from_sql(*, url=None, engine=None, prefix="", namespace=None)
```

Import package from SQL

**Arguments**:

- `url?` _string_ - SQL connection string
- `engine?` _object_ - `sqlalchemy` engine
- `prefix?` _str_ - prefix for all tables
- `namespace?` _str_ - SQL scheme

### package.from\_pandas

```python
 | @staticmethod
 | from_pandas(*, dataframes)
```

Import package from Pandas dataframes

**Arguments**:

- `dataframes` _dict_ - mapping of Pandas dataframes

### package.from\_spss

```python
 | @staticmethod
 | from_spss(*, basepath)
```

Import package from SPSS directory

**Arguments**:

- `basepath` _str_ - SPSS dir path

### package.from\_bigquery

```python
 | @staticmethod
 | from_bigquery(*, service, project, dataset, prefix="")
```

Import package from Bigquery

**Arguments**:

- `service` _object_ - BigQuery `Service` object
- `project` _str_ - BigQuery project name
- `dataset` _str_ - BigQuery dataset name
- `prefix?` _str_ - prefix for all names

### package.to\_copy

```python
 | to_copy()
```

Create a copy of the package

### package.to\_zip

```python
 | to_zip(path, *, resolve=[], encoder_class=None)
```

Save package to a zip

**Arguments**:

- `path` _str_ - target path
- `resolve` _str[]_ - Data sources to resolve.
  For "memory" data it means saving them as CSV and including into ZIP.
  For "remote" data it means downloading them and including into ZIP.
  For example, `resolve=["memory", "remote"]`
- `encoder_class` _object_ - json encoder class
  

**Raises**:

- `FrictionlessException` - on any error

### package.to\_storage

```python
 | to_storage(storage, *, force=False)
```

Export package to storage

**Arguments**:

- `storage` _Storage_ - storage instance
- `force` _bool_ - overwrite existent

### package.to\_ckan

```python
 | to_ckan(*, url, dataset, apikey=None, force=False)
```

Export package to CKAN

**Arguments**:

- `url` _string_ - CKAN instance url e.g. "https://demo.ckan.org"
- `dataset` _string_ - dataset id in CKAN e.g. "my-dataset"
- `apikey?` _str_ - API key for CKAN e.g. "51912f57-a657-4caa-b2a7-0a1c16821f4b"
- `force` _bool_ - (optional) overwrite existing data

### package.to\_sql

```python
 | to_sql(*, url=None, engine=None, prefix="", namespace=None, force=False)
```

Export package to SQL

**Arguments**:

- `url?` _string_ - SQL connection string
- `engine?` _object_ - `sqlalchemy` engine
- `prefix?` _str_ - prefix for all tables
- `namespace?` _str_ - SQL scheme
- `force` _bool_ - overwrite existent

### package.to\_pandas

```python
 | to_pandas()
```

Export package to Pandas dataframes

### package.to\_spss

```python
 | to_spss(*, basepath, force=False)
```

Export package to SPSS directory

**Arguments**:

- `basepath` _str_ - SPSS dir path
- `force` _bool_ - overwrite existent

### package.to\_bigquery

```python
 | to_bigquery(*, service, project, dataset, prefix="", force=False)
```

Export package to Bigquery

**Arguments**:

- `service` _object_ - BigQuery `Service` object
- `project` _str_ - BigQuery project name
- `dataset` _str_ - BigQuery dataset name
- `prefix?` _str_ - prefix for all names
- `force` _bool_ - overwrite existent

## PandasDialect

```python
class PandasDialect(Dialect)
```

Pandas dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.pandas import PandasDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## PandasParser

```python
class PandasParser(Parser)
```

Pandas parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.pandas import PandasParser`

## PandasPlugin

```python
class PandasPlugin(Plugin)
```

Plugin for Pandas

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.pandas import PandasPlugin`

## PandasStorage

```python
class PandasStorage(Storage)
```

Pandas storage implementation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.pandas import PandasStorage`

**Arguments**:

- `dataframes?` _dict_ - dictionary of Pandas dataframes

## Parser

```python
class Parser()
```

Parser representation

API      | Usage
-------- | --------
Public   | `from frictionless import Parser`

**Arguments**:

- `resource` _Resource_ - resource

### parser.resource

```python
 | @property
 | resource()
```

**Returns**:

- `Resource` - resource

### parser.loader

```python
 | @property
 | loader()
```

**Returns**:

- `Loader` - loader

### parser.data\_stream

```python
 | @property
 | data_stream()
```

**Yields**:

- `any[][]` - data stream

### parser.open

```python
 | open()
```

Open the parser as "io.open" does

### parser.close

```python
 | close()
```

Close the parser as "filelike.close" does

### parser.closed

```python
 | @property
 | closed()
```

Whether the parser is closed

**Returns**:

- `bool` - if closed

### parser.read\_loader

```python
 | read_loader()
```

Create and open loader

**Returns**:

- `Loader` - loader

### parser.read\_data\_stream

```python
 | read_data_stream()
```

Read data stream

**Returns**:

- `gen<any[][]>` - data stream

### parser.read\_data\_stream\_create

```python
 | read_data_stream_create(loader)
```

Create data stream from loader

**Arguments**:

- `loader` _Loader_ - loader
  

**Returns**:

- `gen<any[][]>` - data stream

### parser.read\_data\_stream\_handle\_errors

```python
 | read_data_stream_handle_errors(data_stream)
```

Wrap data stream into error handler

**Arguments**:

- `gen<any[][]>` - data stream
  

**Returns**:

- `gen<any[][]>` - data stream

### parser.write\_row\_stream

```python
 | write_row_stream(read_row_stream)
```

Write row stream into the resource

**Arguments**:

- `read_row_stream` _gen<Row[]>_ - row stream factory

## Pipeline

```python
class Pipeline(Metadata)
```

Pipeline representation.

**Arguments**:

- `descriptor?` _str|dict_ - pipeline descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### pipeline.tasks

```python
 | @property
 | tasks()
```

**Returns**:

- `dict[]` - tasks

### pipeline.run

```python
 | run(*, parallel=False)
```

Run the pipeline

## PipelineTask

```python
class PipelineTask(Metadata)
```

Pipeline task representation.

**Arguments**:

- `descriptor?` _str|dict_ - pipeline task descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### pipelineTask.run

```python
 | run()
```

Run the task

## Plugin

```python
class Plugin()
```

Plugin representation

API      | Usage
-------- | --------
Public   | `from frictionless import Plugin`

It's an interface for writing Frictionless plugins.
You can implement one or more methods to hook into Frictionless system.

### plugin.create\_check

```python
 | create_check(name, *, descriptor=None)
```

Create checks

**Arguments**:

- `name` _str_ - check name
- `descriptor` _dict_ - check descriptor
  

**Returns**:

- `Check` - check

### plugin.create\_control

```python
 | create_control(file, *, descriptor)
```

Create control

**Arguments**:

- `file` _File_ - control file
- `descriptor` _dict_ - control descriptor
  

**Returns**:

- `Control` - control

### plugin.create\_dialect

```python
 | create_dialect(file, *, descriptor)
```

Create dialect

**Arguments**:

- `file` _File_ - dialect file
- `descriptor` _dict_ - dialect descriptor
  

**Returns**:

- `Dialect` - dialect

### plugin.create\_loader

```python
 | create_loader(file)
```

Create loader

**Arguments**:

- `file` _File_ - loader file
  

**Returns**:

- `Loader` - loader

### plugin.create\_parser

```python
 | create_parser(file)
```

Create parser

**Arguments**:

- `file` _File_ - parser file
  

**Returns**:

- `Parser` - parser

### plugin.create\_server

```python
 | create_server(name)
```

Create server

**Arguments**:

- `name` _str_ - server name
  

**Returns**:

- `Server` - server

## RemoteControl

```python
class RemoteControl(Control)
```

Remote control representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.remote import RemoteControl`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `http_session?` _requests.Session_ - user defined HTTP session
- `http_preload?` _bool_ - don't use HTTP streaming and preload all the data
- `http_timeout?` _int_ - user defined HTTP timeout in minutes
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### remoteControl.http\_session

```python
 | @Metadata.property
 | http_session()
```

**Returns**:

- `requests.Session` - HTTP session

### remoteControl.http\_preload

```python
 | @Metadata.property
 | http_preload()
```

**Returns**:

- `bool` - if not streaming

### remoteControl.http\_timeout

```python
 | @Metadata.property
 | http_timeout()
```

**Returns**:

- `int` - HTTP timeout in minutes

### remoteControl.expand

```python
 | expand()
```

Expand metadata

## RemoteLoader

```python
class RemoteLoader(Loader)
```

Remote loader implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.remote import RemoteLoader`

## RemotePlugin

```python
class RemotePlugin(Plugin)
```

Plugin for Remote Data

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.remote import RemotePlugin`

## Report

```python
class Report(Metadata)
```

Report representation.

API      | Usage
-------- | --------
Public   | `from frictionless import Report`

**Arguments**:

- `descriptor?` _str|dict_ - report descriptor
- `time` _float_ - validation time
- `errors` _Error[]_ - validation errors
- `tasks` _ReportTask[]_ - validation tasks
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### report.version

```python
 | @property
 | version()
```

**Returns**:

- `str` - frictionless version

### report.time

```python
 | @property
 | time()
```

**Returns**:

- `float` - validation time

### report.valid

```python
 | @property
 | valid()
```

**Returns**:

- `bool` - validation result

### report.stats

```python
 | @property
 | stats()
```

**Returns**:

- `dict` - validation stats

### report.errors

```python
 | @property
 | errors()
```

**Returns**:

- `Error[]` - validation errors

### report.tasks

```python
 | @property
 | tasks()
```

**Returns**:

- `ReportTask[]` - validation tasks

### report.task

```python
 | @property
 | task()
```

**Returns**:

- `ReportTask` - validation task (if there is only one)
  

**Raises**:

- `FrictionlessException` - if there are more that 1 task

### report.expand

```python
 | expand()
```

Expand metadata

### report.flatten

```python
 | flatten(spec=["taskPosition", "rowPosition", "fieldPosition", "code"])
```

Flatten the report

Parameters
spec (any[]): flatten specification

**Returns**:

- `any[]` - flatten report

### report.from\_validate

```python
 | @staticmethod
 | from_validate(validate)
```

Validate function wrapper

**Arguments**:

- `validate` _func_ - validate
  

**Returns**:

- `func` - wrapped validate

## ReportTask

```python
class ReportTask(Metadata)
```

Report task representation.

API      | Usage
-------- | --------
Public   | `from frictionless import ReportTask`

**Arguments**:

- `descriptor?` _str|dict_ - schema descriptor
- `time` _float_ - validation time
- `scope` _str[]_ - validation scope
- `partial` _bool_ - wehter validation was partial
- `errors` _Error[]_ - validation errors
- `task` _Task_ - validation task
  
  # Raises
- `FrictionlessException` - raise any error that occurs during the process

### reportTask.resource

```python
 | @property
 | resource()
```

**Returns**:

- `Resource` - resource

### reportTask.time

```python
 | @property
 | time()
```

**Returns**:

- `float` - validation time

### reportTask.valid

```python
 | @property
 | valid()
```

**Returns**:

- `bool` - validation result

### reportTask.scope

```python
 | @property
 | scope()
```

**Returns**:

- `str[]` - validation scope

### reportTask.partial

```python
 | @property
 | partial()
```

**Returns**:

- `bool` - if validation partial

### reportTask.stats

```python
 | @property
 | stats()
```

**Returns**:

- `dict` - validation stats

### reportTask.errors

```python
 | @property
 | errors()
```

**Returns**:

- `Error[]` - validation errors

### reportTask.error

```python
 | @property
 | error()
```

**Returns**:

- `Error` - validation error if there is only one
  

**Raises**:

- `FrictionlessException` - if more than one errors

### reportTask.expand

```python
 | expand()
```

Expand metadata

### reportTask.flatten

```python
 | flatten(spec=["rowPosition", "fieldPosition", "code"])
```

Flatten the report

Parameters
spec (any[]): flatten specification

**Returns**:

- `any[]` - flatten task report

## Resource

```python
class Resource(Metadata)
```

Resource representation.

API      | Usage
-------- | --------
Public   | `from frictionless import Resource`

This class is one of the cornerstones of of Frictionless framework.
It loads a data source, and allows you to stream its parsed contents.
At the same time, it's a metadata class data description.


```python
with Resource("data/table.csv") as resource:
    resource.header == ["id", "name"]
    resource.read_rows() == [
        {'id': 1, 'name': 'english'},
        {'id': 2, 'name': '?????????'},
    ]
```

**Arguments**:

  
- `source` _any_ - Source of the resource; can be in various forms.
  Usually, it's a string as `<scheme>://path/to/file.<format>`.
  It also can be, for example, an array of data arrays/dictionaries.
  Or it can be a resource descriptor dict or path.
  
- `descriptor` _dict|str_ - A resource descriptor provided explicitly.
  Keyword arguments will patch this descriptor if provided.
  
- `name?` _str_ - A Resource name according to the specs.
  It should be a slugified name of the resource.
  
- `title?` _str_ - A Resource title according to the specs
  It should a human-oriented title of the resource.
  
- `description?` _str_ - A Resource description according to the specs
  It should a human-oriented description of the resource.
  
- `mediatype?` _str_ - A mediatype/mimetype of the resource e.g. ???text/csv???,
  or ???application/vnd.ms-excel???.  Mediatypes are maintained by the
  Internet Assigned Numbers Authority (IANA) in a media type registry.
  
- `licenses?` _dict[]_ - The license(s) under which the resource is provided.
  If omitted it's considered the same as the package's licenses.
  
- `sources?` _dict[]_ - The raw sources for this data resource.
  It MUST be an array of Source objects.
  Each Source object MUST have a title and
  MAY have path and/or email properties.
  
- `profile?` _str_ - A string identifying the profile of this descriptor.
  For example, `tabular-data-resource`.
  
- `scheme?` _str_ - Scheme for loading the file (file, http, ...).
  If not set, it'll be inferred from `source`.
  
- `format?` _str_ - File source's format (csv, xls, ...).
  If not set, it'll be inferred from `source`.
  
- `hashing?` _str_ - An algorithm to hash data.
  It defaults to 'md5'.
  
- `encoding?` _str_ - Source encoding.
  If not set, it'll be inferred from `source`.
  
- `innerpath?` _str_ - A path within the compressed file.
  It defaults to the first file in the archive.
  
- `compression?` _str_ - Source file compression (zip, ...).
  If not set, it'll be inferred from `source`.
  
- `control?` _dict|Control_ - File control.
  For more information, please check the Control documentation.
  
- `dialect?` _dict|Dialect_ - Table dialect.
  For more information, please check the Dialect documentation.
  
- `layout?` _dict|Layout_ - Table layout.
  For more information, please check the Layout documentation.
  
- `schema?` _dict|Schema_ - Table schema.
  For more information, please check the Schema documentation.
  
- `stats?` _dict_ - File/table stats.
  A dict with the following possible properties: hash, bytes, fields, rows.
  
- `basepath?` _str_ - A basepath of the resource
  The fullpath of the resource is joined `basepath` and /path`
  
- `detector?` _Detector_ - File/table detector.
  For more information, please check the Detector documentation.
  
- `onerror?` _ignore|warn|raise_ - Behaviour if there is an error.
  It defaults to 'ignore'. The default mode will ignore all errors
  on resource level and they should be handled by the user
  being available in Header and Row objects.
  
- `trusted?` _bool_ - Don't raise an exception on unsafe paths.
  A path provided as a part of the descriptor considered unsafe
  if there are path traversing or the path is absolute.
  A path provided as `source` or `path` is alway trusted.
  
- `nolookup?` _bool_ - Don't create a lookup table.
  A lookup table can be required by foreign keys.
  
- `package?` _Package_ - A owning this resource package.
  It's actual if the resource is part of some data package.
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### resource.name

```python
 | @Metadata.property
 | name()
```

Returns
    str: resource name

### resource.title

```python
 | @Metadata.property
 | title()
```

Returns
    str: resource title

### resource.description

```python
 | @Metadata.property
 | description()
```

Returns
    str: resource description

### resource.mediatype

```python
 | @Metadata.property
 | mediatype()
```

Returns
    str: resource mediatype

### resource.licenses

```python
 | @Metadata.property
 | licenses()
```

Returns
    dict[]: resource licenses

### resource.sources

```python
 | @Metadata.property
 | sources()
```

Returns
    dict[]: resource sources

### resource.profile

```python
 | @Metadata.property
 | profile()
```

Returns
    str?: resource profile

### resource.path

```python
 | @Metadata.property
 | path()
```

Returns
    str?: resource path

### resource.data

```python
 | @Metadata.property
 | data()
```

Returns
    any[][]?: resource data

### resource.scheme

```python
 | @Metadata.property
 | scheme()
```

Returns
    str?: resource scheme

### resource.format

```python
 | @Metadata.property
 | format()
```

Returns
    str?: resource format

### resource.hashing

```python
 | @Metadata.property
 | hashing()
```

Returns
    str?: resource hashing

### resource.encoding

```python
 | @Metadata.property
 | encoding()
```

Returns
    str?: resource encoding

### resource.innerpath

```python
 | @Metadata.property
 | innerpath()
```

Returns
    str?: resource compression path

### resource.compression

```python
 | @Metadata.property
 | compression()
```

Returns
    str?: resource compression

### resource.control

```python
 | @Metadata.property
 | control()
```

Returns
    Control?: resource control

### resource.dialect

```python
 | @Metadata.property
 | dialect()
```

Returns
    Dialect?: resource dialect

### resource.layout

```python
 | @Metadata.property
 | layout()
```

**Returns**:

- `Layout?` - table layout

### resource.schema

```python
 | @Metadata.property
 | schema()
```

Returns
    Schema: resource schema

### resource.sample

```python
 | @property
 | sample()
```

Tables's rows used as sample.

These sample rows are used internally to infer characteristics of the
source file (e.g. schema, ...).

**Returns**:

- `list[]?` - table sample

### resource.labels

```python
 | @property
 | labels()
```

**Returns**:

- `str[]?` - table labels

### resource.header

```python
 | @property
 | header()
```

**Returns**:

- `str[]?` - table header

### resource.lookup

```python
 | @property
 | lookup()
```

**Returns**:

- `any?` - table lookup

### resource.stats

```python
 | @Metadata.property
 | stats()
```

Returns
    dict?: resource stats

### resource.basepath

```python
 | @Metadata.property(cache=False, write=False)
 | basepath()
```

Returns
    str: resource basepath

### resource.fullpath

```python
 | @Metadata.property(cache=False, write=False)
 | fullpath()
```

Returns
    str: resource fullpath

### resource.detector

```python
 | @Metadata.property(cache=False, write=False)
 | detector()
```

Returns
    str: resource detector

### resource.onerror

```python
 | @Metadata.property(cache=False, write=False)
 | onerror()
```

**Returns**:

- `ignore|warn|raise` - on error bahaviour

### resource.trusted

```python
 | @Metadata.property(cache=False, write=False)
 | trusted()
```

**Returns**:

- `bool` - don't raise an exception on unsafe paths

### resource.package

```python
 | @Metadata.property(cache=False, write=False)
 | package()
```

**Returns**:

- `Package?` - parent package

### resource.memory

```python
 | @Metadata.property(write=False)
 | memory()
```

Returns
    bool: if resource is memory

### resource.remote

```python
 | @Metadata.property(write=False)
 | remote()
```

Returns
    bool: if resource is remote

### resource.multipart

```python
 | @Metadata.property(write=False)
 | multipart()
```

Returns
    bool: if resource is multipart

### resource.tabular

```python
 | @Metadata.property(write=False)
 | tabular()
```

Returns
    bool: if resource is tabular

### resource.byte\_stream

```python
 | @property
 | byte_stream()
```

Byte stream in form of a generator

**Yields**:

- `gen<bytes>?` - byte stream

### resource.text\_stream

```python
 | @property
 | text_stream()
```

Text stream in form of a generator

**Yields**:

- `gen<str[]>?` - data stream

### resource.data\_stream

```python
 | @property
 | data_stream()
```

Data stream in form of a generator

**Yields**:

- `gen<any[][]>?` - data stream

### resource.row\_stream

```python
 | @property
 | row_stream()
```

Row stream in form of a generator of Row objects

**Yields**:

- `gen<Row[]>?` - row stream

### resource.expand

```python
 | expand()
```

Expand metadata

### resource.infer

```python
 | infer(*, stats=False)
```

Infer metadata

**Arguments**:

- `stats?` _bool_ - stream file completely and infer stats

### resource.open

```python
 | open()
```

Open the resource as "io.open" does

**Raises**:

- `FrictionlessException` - any exception that occurs

### resource.close

```python
 | close()
```

Close the table as "filelike.close" does

### resource.closed

```python
 | @property
 | closed()
```

Whether the table is closed

**Returns**:

- `bool` - if closed

### resource.read\_bytes

```python
 | read_bytes(*, size=None)
```

Read data into memory

**Returns**:

- `any[][]` - table data

### resource.read\_text

```python
 | read_text(*, size=None)
```

Read text into memory

**Returns**:

- `str` - table data

### resource.read\_data

```python
 | read_data(*, size=None)
```

Read data into memory

**Returns**:

- `any[][]` - table data

### resource.read\_rows

```python
 | read_rows(*, size=None)
```

Read rows into memory

**Returns**:

- `Row[]` - table rows

### resource.write

```python
 | write(target)
```

Write this resource to the target resource

**Arguments**:

- `target` _Resource_ - target Resource

### resource.from\_petl

```python
 | @staticmethod
 | from_petl(storage, *, view, **options)
```

Create a resource from PETL container

### resource.from\_storage

```python
 | @staticmethod
 | from_storage(storage, *, name)
```

Import resource from storage

**Arguments**:

- `storage` _Storage_ - storage instance
- `name` _str_ - resource name

### resource.from\_ckan

```python
 | @staticmethod
 | from_ckan(*, name, url, dataset, apikey=None)
```

Import resource from CKAN

**Arguments**:

- `name` _string_ - resource name
- `url` _string_ - CKAN instance url e.g. "https://demo.ckan.org"
- `dataset` _string_ - dataset id in CKAN e.g. "my-dataset"
- `apikey?` _str_ - API key for CKAN e.g. "51912f57-a657-4caa-b2a7-0a1c16821f4b"

### resource.from\_sql

```python
 | @staticmethod
 | from_sql(*, name, url=None, engine=None, prefix="", namespace=None)
```

Import resource from SQL table

**Arguments**:

- `name` _str_ - resource name
- `url?` _string_ - SQL connection string
- `engine?` _object_ - `sqlalchemy` engine
- `prefix?` _str_ - prefix for all tables
- `namespace?` _str_ - SQL scheme

### resource.from\_pandas

```python
 | @staticmethod
 | from_pandas(dataframe)
```

Import resource from Pandas dataframe

**Arguments**:

- `dataframe` _str_ - padas dataframe

### resource.from\_spss

```python
 | @staticmethod
 | from_spss(*, name, basepath)
```

Import resource from SPSS file

**Arguments**:

- `name` _str_ - resource name
- `basepath` _str_ - SPSS dir path

### resource.from\_bigquery

```python
 | @staticmethod
 | from_bigquery(*, name, service, project, dataset, prefix="")
```

Import resource from BigQuery table

**Arguments**:

- `name` _str_ - resource name
- `service` _object_ - BigQuery `Service` object
- `project` _str_ - BigQuery project name
- `dataset` _str_ - BigQuery dataset name
- `prefix?` _str_ - prefix for all names

### resource.to\_copy

```python
 | to_copy(**options)
```

Create a copy of the resource

### resource.to\_storage

```python
 | to_storage(storage, *, force=False)
```

Export resource to storage

**Arguments**:

- `storage` _Storage_ - storage instance
- `force` _bool_ - overwrite existent

### resource.to\_ckan

```python
 | to_ckan(*, url, dataset, apikey=None, force=False)
```

Export resource to CKAN

**Arguments**:

- `url` _string_ - CKAN instance url e.g. "https://demo.ckan.org"
- `dataset` _string_ - dataset id in CKAN e.g. "my-dataset"
- `apikey?` _str_ - API key for CKAN e.g. "51912f57-a657-4caa-b2a7-0a1c16821f4b"
- `force` _bool_ - (optional) overwrite existing data

### resource.to\_sql

```python
 | to_sql(*, url=None, engine=None, prefix="", namespace=None, force=False)
```

Export resource to SQL table

**Arguments**:

- `url?` _string_ - SQL connection string
- `engine?` _object_ - `sqlalchemy` engine
- `prefix?` _str_ - prefix for all tables
- `namespace?` _str_ - SQL scheme
- `force?` _bool_ - overwrite existent

### resource.to\_pandas

```python
 | to_pandas()
```

Export resource to Pandas dataframe

**Arguments**:

- `dataframes` _dict_ - pandas dataframes
- `force` _bool_ - overwrite existent

### resource.to\_spss

```python
 | to_spss(*, basepath, force=False)
```

Export resource to SPSS file

**Arguments**:

- `basepath` _str_ - SPSS dir path
- `force` _bool_ - overwrite existent

### resource.to\_bigquery

```python
 | to_bigquery(*, service, project, dataset, prefix="", force=False)
```

Export resource to Bigquery table

**Arguments**:

- `service` _object_ - BigQuery `Service` object
- `project` _str_ - BigQuery project name
- `dataset` _str_ - BigQuery dataset name
- `prefix?` _str_ - prefix for all names
- `force` _bool_ - overwrite existent

## Row

```python
class Row(dict)
```

Row representation

API      | Usage
-------- | --------
Public   | `from frictionless import Row`

> Constructor of this object is not Public API

This object is returned by `extract`, `resource.read_rows`, and other functions.


```python
rows = extract("data/table.csv")
for row in rows:
    # work with the Row
```

**Arguments**:

- `cells` _any[]_ - array of cells
- `field_info` _dict_ - special field info structure
- `row_position` _int_ - row position from 1
- `row_number` _int_ - row number from 1

### row.cells

```python
 | @cached_property
 | cells()
```

**Returns**:

- `Field[]` - table schema fields

### row.fields

```python
 | @cached_property
 | fields()
```

**Returns**:

- `Field[]` - table schema fields

### row.field\_names

```python
 | @cached_property
 | field_names()
```

**Returns**:

- `Schema` - table schema

### row.field\_positions

```python
 | @cached_property
 | field_positions()
```

**Returns**:

- `int[]` - table field positions

### row.row\_position

```python
 | @cached_property
 | row_position()
```

**Returns**:

- `int` - row position from 1

### row.row\_number

```python
 | @cached_property
 | row_number()
```

**Returns**:

- `int` - row number from 1

### row.blank\_cells

```python
 | @cached_property
 | blank_cells()
```

A mapping indexed by a field name with blank cells before parsing

**Returns**:

- `dict` - row blank cells

### row.error\_cells

```python
 | @cached_property
 | error_cells()
```

A mapping indexed by a field name with error cells before parsing

**Returns**:

- `dict` - row error cells

### row.errors

```python
 | @cached_property
 | errors()
```

**Returns**:

- `Error[]` - row errors

### row.valid

```python
 | @cached_property
 | valid()
```

**Returns**:

- `bool` - if row valid

### row.to\_str

```python
 | to_str()
```

**Returns**:

- `str` - a row as a CSV string

### row.to\_list

```python
 | to_list(*, json=False, types=None)
```

**Arguments**:

- `json` _bool_ - make data types compatible with JSON format
- `types` _str[]_ - list of supported types
  

**Returns**:

- `dict` - a row as a list

### row.to\_dict

```python
 | to_dict(*, json=False, types=None)
```

**Arguments**:

- `json` _bool_ - make data types compatible with JSON format
  

**Returns**:

- `dict` - a row as a dictionary

## RowError

```python
class RowError(TableError)
```

Row error representation

**Arguments**:

- `descriptor?` _str|dict_ - error descriptor
- `note` _str_ - an error note
- `row_number` _int_ - row number
- `row_position` _int_ - row position
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### rowError.from\_row

```python
 | @classmethod
 | from_row(cls, row, *, note)
```

Create an error from a row

**Arguments**:

- `row` _Row_ - row
- `note` _str_ - note
  

**Returns**:

- `RowError` - error

## S3Control

```python
class S3Control(Control)
```

S3 control representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.s3 import S3Control`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `endpoint_url?` _string_ - endpoint url
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### s3Control.expand

```python
 | expand()
```

Expand metadata

## S3Loader

```python
class S3Loader(Loader)
```

S3 loader implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.s3 import S3Loader`

## S3Plugin

```python
class S3Plugin(Plugin)
```

Plugin for S3

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.s3 import S3Plugin`

## Schema

```python
class Schema(Metadata)
```

Schema representation

API      | Usage
-------- | --------
Public   | `from frictionless import Schema`

This class is one of the cornerstones of of Frictionless framework.
It allow to work with Table Schema and its fields.


```python
schema = Schema('schema.json')
schema.add_fied(Field(name='name', type='string'))
```

**Arguments**:

- `descriptor?` _str|dict_ - schema descriptor
- `fields?` _dict[]_ - list of field descriptors
- `missing_values?` _str[]_ - missing values
- `primary_key?` _str[]_ - primary key
- `foreign_keys?` _dict[]_ - foreign keys
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### schema.missing\_values

```python
 | @Metadata.property
 | missing_values()
```

**Returns**:

- `str[]` - missing values

### schema.primary\_key

```python
 | @Metadata.property
 | primary_key()
```

**Returns**:

- `str[]` - primary key field names

### schema.foreign\_keys

```python
 | @Metadata.property
 | foreign_keys()
```

**Returns**:

- `dict[]` - foreign keys

### schema.fields

```python
 | @Metadata.property
 | fields()
```

**Returns**:

- `Field[]` - an array of field instances

### schema.field\_names

```python
 | @Metadata.property(cache=False, write=False)
 | field_names()
```

**Returns**:

- `str[]` - an array of field names

### schema.add\_field

```python
 | add_field(descriptor)
```

Add new field to schema.

The schema descriptor will be validated with newly added field descriptor.

**Arguments**:

- `descriptor` _dict_ - field descriptor
  

**Returns**:

- `Field/None` - added `Field` instance or `None` if not added

### schema.get\_field

```python
 | get_field(name)
```

Get schema's field by name.

**Arguments**:

- `name` _str_ - schema field name
  

**Raises**:

- `FrictionlessException` - if field is not found
  

**Returns**:

- `Field` - `Field` instance or `None` if not found

### schema.has\_field

```python
 | has_field(name)
```

Check if a field is present

**Arguments**:

- `name` _str_ - schema field name
  

**Returns**:

- `bool` - whether there is the field

### schema.remove\_field

```python
 | remove_field(name)
```

Remove field by name.

The schema descriptor will be validated after field descriptor removal.

**Arguments**:

- `name` _str_ - schema field name
  

**Raises**:

- `FrictionlessException` - if field is not found
  

**Returns**:

- `Field/None` - removed `Field` instances or `None` if not found

### schema.expand

```python
 | expand()
```

Expand the schema

### schema.read\_cells

```python
 | read_cells(cells)
```

Read a list of cells (normalize/cast)

**Arguments**:

- `cells` _any[]_ - list of cells
  

**Returns**:

- `any[]` - list of processed cells

### schema.write\_cells

```python
 | write_cells(cells, *, types=[])
```

Write a list of cells (normalize/uncast)

**Arguments**:

- `cells` _any[]_ - list of cells
  

**Returns**:

- `any[]` - list of processed cells

## Server

```python
class Server()
```

Server representation

API      | Usage
-------- | --------
Public   | `from frictionless import Schema`

### server.start

```python
 | start(port)
```

Start the server

**Arguments**:

- `port` _int_ - HTTP port

### server.stop

```python
 | stop()
```

Stop the server

## ServerPlugin

```python
class ServerPlugin(Plugin)
```

Plugin for Server

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.server import ServerPlugin`

## SpssDialect

```python
class SpssDialect(Dialect)
```

Spss dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.spss import SpssDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## SpssParser

```python
class SpssParser(Parser)
```

Spss parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.spss import SpssParser`

## SpssPlugin

```python
class SpssPlugin(Plugin)
```

Plugin for SPSS

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.spss import SpssPlugin`

## SpssStorage

```python
class SpssStorage(Storage)
```

SPSS storage implementation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.spss import SpssStorage`

**Arguments**:

- `basepath?` _str_ - A path to a dir for reading/writing SAV files.
  Defaults to current dir.

## SqlDialect

```python
class SqlDialect(Dialect)
```

SQL dialect representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.sql import SqlDialect`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
- `table` _str_ - table
- `order_by?` _str_ - order_by
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## SqlParser

```python
class SqlParser(Parser)
```

SQL parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.sql import SqlParser`

## SqlPlugin

```python
class SqlPlugin(Plugin)
```

Plugin for SQL

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.sql import SqlPlugin`

## SqlStorage

```python
class SqlStorage(Storage)
```

SQL storage implementation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.sql import SqlStorage`

**Arguments**:

- `url?` _string_ - SQL connection string
- `engine?` _object_ - `sqlalchemy` engine
- `prefix?` _str_ - prefix for all tables
- `namespace?` _str_ - SQL scheme

## Status

```python
class Status(Metadata)
```

Status representation.

**Arguments**:

- `descriptor?` _str|dict_ - schema descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

### status.version

```python
 | @property
 | version()
```

**Returns**:

- `str` - frictionless version

### status.time

```python
 | @property
 | time()
```

**Returns**:

- `float` - validation time

### status.valid

```python
 | @property
 | valid()
```

**Returns**:

- `bool` - validation result

### status.stats

```python
 | @property
 | stats()
```

**Returns**:

- `dict` - validation stats

### status.errors

```python
 | @property
 | errors()
```

**Returns**:

- `Error[]` - validation errors

### status.tasks

```python
 | @property
 | tasks()
```

**Returns**:

- `ReportTable[]` - validation tasks

### status.task

```python
 | @property
 | task()
```

**Returns**:

- `ReportTable` - validation task (if there is only one)
  

**Raises**:

- `FrictionlessException` - if there are more that 1 task

## StatusTask

```python
class StatusTask(Metadata)
```

Status Task representation

### statusTask.valid

```python
 | @property
 | valid()
```

**Returns**:

- `bool` - validation result

### statusTask.errors

```python
 | @property
 | errors()
```

**Returns**:

- `Error[]` - validation errors

### statusTask.target

```python
 | @property
 | target()
```

**Returns**:

- `any` - validation target

### statusTask.type

```python
 | @property
 | type()
```

**Returns**:

- `any` - validation target

## Storage

```python
class Storage()
```

Storage representation

## StringType

```python
class StringType(Type)
```

String type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## System

```python
class System()
```

System representation

API      | Usage
-------- | --------
Public   | `from frictionless import system`

This class provides an ability to make system Frictionless calls.
It's available as `frictionless.system` singletone.

### system.register

```python
 | register(name, plugin)
```

Register a plugin

**Arguments**:

- `name` _str_ - plugin name
- `plugin` _Plugin_ - plugin to register

### system.create\_check

```python
 | create_check(descriptor)
```

Create checks

**Arguments**:

- `descriptor` _dict_ - check descriptor
  

**Returns**:

- `Check` - check

### system.create\_control

```python
 | create_control(resource, *, descriptor)
```

Create control

**Arguments**:

- `resource` _Resource_ - control resource
- `descriptor` _dict_ - control descriptor
  

**Returns**:

- `Control` - control

### system.create\_dialect

```python
 | create_dialect(resource, *, descriptor)
```

Create dialect

**Arguments**:

- `resource` _Resource_ - dialect resource
- `descriptor` _dict_ - dialect descriptor
  

**Returns**:

- `Dialect` - dialect

### system.create\_file

```python
 | create_file(source, **options)
```

Create file

**Arguments**:

- `source` _any_ - file source
- `options` _dict_ - file options
  

**Returns**:

- `File` - file

### system.create\_loader

```python
 | create_loader(resource)
```

Create loader

**Arguments**:

- `resource` _Resource_ - loader resource
  

**Returns**:

- `Loader` - loader

### system.create\_parser

```python
 | create_parser(resource)
```

Create parser

**Arguments**:

- `resource` _Resource_ - parser resource
  

**Returns**:

- `Parser` - parser

### system.create\_server

```python
 | create_server(name, **options)
```

Create server

**Arguments**:

- `name` _str_ - server name
- `options` _str_ - server options
  

**Returns**:

- `Server` - server

### system.create\_step

```python
 | create_step(descriptor)
```

Create steps

**Arguments**:

- `descriptor` _dict_ - step descriptor
  

**Returns**:

- `Step` - step

### system.create\_storage

```python
 | create_storage(name, **options)
```

Create storage

**Arguments**:

- `name` _str_ - storage name
- `options` _str_ - storage options
  

**Returns**:

- `Storage` - storage

### system.create\_type

```python
 | create_type(field)
```

Create checks

**Arguments**:

- `field` _Field_ - corresponding field
  

**Returns**:

- `Type` - type

## TextControl

```python
class TextControl(Control)
```

Text control representation

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.text import TextControl`

**Arguments**:

- `descriptor?` _str|dict_ - descriptor
  

**Raises**:

- `FrictionlessException` - raise any error that occurs during the process

## TextLoader

```python
class TextLoader(Loader)
```

Text loader implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.text import TextLoader`

## TextPlugin

```python
class TextPlugin(Plugin)
```

Plugin for Text Data

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.local import TextPlugin`

## TimeType

```python
class TimeType(Type)
```

Time type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## Type

```python
class Type()
```

Data type representation

API      | Usage
-------- | --------
Public   | `from frictionless import Type`

This class is for subclassing.

**Arguments**:

- `field` _Field_ - field

### type.constraints

**Returns**:

- `str[]` - a list of supported constraints

### type.field

```python
 | @cached_property
 | field()
```

**Returns**:

- `Field` - field

### type.read\_cell

```python
 | read_cell(cell)
```

Convert cell (read direction)

**Arguments**:

- `cell` _any_ - cell to covert
  

**Returns**:

- `any` - converted cell

### type.write\_cell

```python
 | write_cell(cell)
```

Convert cell (write direction)

**Arguments**:

- `cell` _any_ - cell to covert
  

**Returns**:

- `any` - converted cell

## XlsParser

```python
class XlsParser(Parser)
```

XLS parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.excel import XlsParser

## XlsxParser

```python
class XlsxParser(Parser)
```

XLSX parser implementation.

API      | Usage
-------- | --------
Public   | `from frictionless.plugins.excel import XlsxParser

## YearType

```python
class YearType(Type)
```

Year type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## YearmonthType

```python
class YearmonthType(Type)
```

Yearmonth type implementation.

API      | Usage
-------- | --------
Public   | `from frictionless import types`

## baseline

```python
class baseline(Check)
```

Check a table for basic errors

API      | Usage
-------- | --------
Public   | `from frictionless import checks`
Implicit | `validate(...)`

Ths check is enabled by default for any `validate` function run.

## checksum

```python
class checksum(Check)
```

Check a table's checksum

API      | Usage
-------- | --------
Public   | `from frictionless import checks`
Implicit | `validate(checksum={...})`

Ths check is enabled by default if the `checksum` argument
is provided for the `validate` function.

**Arguments**:

- `descriptor` _dict_ - check's descriptor
- `hash?` _str_ - a hash sum of the table's bytes
- `bytes?` _int_ - number of bytes
- `fields?` _int_ - number of fields
- `rows?` _int_ - number of rows

## describe

```python
describe(source, *, type=None, **options)
```

Describe the data source

API      | Usage
-------- | --------
Public   | `from frictionless import describe`

**Arguments**:

- `source` _any_ - data source
- `type` _str_ - source type - `schema`, `resource` or `package` (default: infer)
- `**options` _dict_ - options for the underlaying describe function
  

**Returns**:

- `Package|Resource|Schema` - metadata

## describe\_package

```python
describe_package(source, *, expand=False, nostats=False, **options)
```

Describe the given source as a package

API      | Usage
-------- | --------
Public   | `from frictionless import describe_package`

**Arguments**:

- `source` _any_ - data source
- `expand?` _bool_ - if `True` it will expand the metadata
- `nostats?` _bool_ - if `True` it not infer resource's stats
- `**options` _dict_ - Package constructor options
  

**Returns**:

- `Package` - data package

## describe\_resource

```python
describe_resource(source, *, expand=False, nostats=False, **options)
```

Describe the given source as a resource

API      | Usage
-------- | --------
Public   | `from frictionless import describe_resource`

**Arguments**:

- `source` _any_ - data source
- `expand?` _bool_ - if `True` it will expand the metadata
- `nostats?` _bool_ - if `True` it not infer resource's stats
- `**options` _dict_ - Resource constructor options
  

**Returns**:

- `Resource` - data resource

## describe\_schema

```python
describe_schema(source, **options)
```

Describe the given source as a schema

API      | Usage
-------- | --------
Public   | `from frictionless import describe_schema`

**Arguments**:

- `source` _any_ - data source
- `**options` _dict_ - describe resource options
  

**Returns**:

- `Schema` - table schema

## deviated\_value

```python
class deviated_value(Check)
```

Check for deviated values in a field

API      | Usage
-------- | --------
Public   | `from frictionless import checks`
Implicit | `validate(checks=([{"code": "deviated-value", **descriptor}])`

This check can be enabled using the `checks` parameter
for the `validate` function.

**Arguments**:

- `descriptor` _dict_ - check's descriptor
- `field_name` _str_ - a field name to check
- `average?` _str_ - one of "mean", "median" or "mode" (default: "mean")
- `interval?` _str_ - statistical interval (default: 3)

## duplicate\_row

```python
class duplicate_row(Check)
```

Check for duplicate rows

API      | Usage
-------- | --------
Public   | `from frictionless import checks`
Implicit | `validate(checks=[{"code": "duplicate-row"}])`

This check can be enabled using the `checks` parameter
for the `validate` function.

## extract

```python
extract(source, *, type=None, process=None, stream=False, **options)
```

Extract resource rows

API      | Usage
-------- | --------
Public   | `from frictionless import extract`

**Arguments**:

- `source` _dict|str_ - data source
- `type` _str_ - source type - package of resource (default: infer)
- `process?` _func_ - a row processor function
- `stream?` _bool_ - return a row stream(s) instead of loading into memory
- `**options` _dict_ - options for the underlaying function
  

**Returns**:

- `Row[]|{path` - Row[]}: rows in a form depending on the source type

## extract\_package

```python
extract_package(source, *, process=None, stream=False, **options)
```

Extract package rows

API      | Usage
-------- | --------
Public   | `from frictionless import extract_package`

**Arguments**:

- `source` _dict|str_ - data resource descriptor
- `process?` _func_ - a row processor function
- `stream?` _bool_ - return a row streams instead of loading into memory
- `**options` _dict_ - Package constructor options
  

**Returns**:

- `{path` - Row[]}: a dictionary of arrays/streams of rows

## extract\_resource

```python
extract_resource(source, *, process=None, stream=False, **options)
```

Extract resource rows

API      | Usage
-------- | --------
Public   | `from frictionless import extract_resource`

**Arguments**:

- `source` _dict|str_ - data resource descriptor
- `process?` _func_ - a row processor function
- `**options` _dict_ - Resource constructor options
  

**Returns**:

- `Row[]` - an array/stream of rows

## forbidden\_value

```python
class forbidden_value(Check)
```

Check for forbidden values in a field

API      | Usage
-------- | --------
Public   | `from frictionless import checks`
Implicit | `validate(checks=[{"code": "backlisted-value", **descriptor}])`

This check can be enabled using the `checks` parameter
for the `validate` function.

**Arguments**:

- `descriptor` _dict_ - check's descriptor
- `field_name` _str_ - a field name to look into
- `forbidden` _any[]_ - a list of forbidden values

## row\_constraint

```python
class row_constraint(Check)
```

Check that every row satisfies a provided Python expression

API      | Usage
-------- | --------
Public   | `from frictionless import checks`
Implicit | `validate(checks=([{"code": "row-constraint", **descriptor}])`

This check can be enabled using the `checks` parameter
for the `validate` function. The syntax for the row constraint
check can be found here - https://github.com/danthedeckie/simpleeval

**Arguments**:

- `descriptor` _dict_ - check's descriptor
- `formula` _str_ - a python expression to evaluate against a row

## sequential\_value

```python
class sequential_value(Check)
```

Check that a column having sequential values

API      | Usage
-------- | --------
Public   | `from frictionless import checks`
Implicit | `validate(checks=[{"code": "sequential-value", **descriptor}])`

This check can be enabled using the `checks` parameter
for the `validate` function.

**Arguments**:

- `descriptor` _dict_ - check's descriptor
- `field_name` _str_ - a field name to check

## transform

```python
transform(source, type=None, **options)
```

Transform resource

API      | Usage
-------- | --------
Public   | `from frictionless import transform`

**Arguments**:

- `source` _any_ - data source
- `type` _str_ - source type - package, resource or pipeline (default: infer)
- `**options` _dict_ - options for the underlaying function
  

**Returns**:

- `any` - the transform result

## transform\_package

```python
transform_package(source, *, steps, **options)
```

Transform package

API      | Usage
-------- | --------
Public   | `from frictionless import transform_package`

**Arguments**:

- `source` _any_ - data source
- `steps` _Step[]_ - transform steps
- `**options` _dict_ - Package constructor options
  

**Returns**:

- `Package` - the transform result

## transform\_pipeline

```python
transform_pipeline(source, *, parallel=False, **options)
```

Transform package

API      | Usage
-------- | --------
Public   | `from frictionless import transform_package`

**Arguments**:

- `source` _any_ - a pipeline descriptor
- `**options` _dict_ - Pipeline constructor options
  

**Returns**:

- `any` - the pipeline output

## transform\_resource

```python
transform_resource(source, *, steps, **options)
```

Transform resource

API      | Usage
-------- | --------
Public   | `from frictionless import transform_resource`

**Arguments**:

- `source` _any_ - data source
- `steps` _Step[]_ - transform steps
- `**options` _dict_ - Package constructor options
  

**Returns**:

- `Resource` - the transform result

## truncated\_value

```python
class truncated_value(Check)
```

Check for possible truncated values

API      | Usage
-------- | --------
Public   | `from frictionless import checks`
Implicit | `validate(checks=([{"code": "truncated-value"}])`

This check can be enabled using the `checks` parameter
for the `validate` function.

## validate

```python
@Report.from_validate
validate(source, type=None, **options)
```

Validate resource

API      | Usage
-------- | --------
Public   | `from frictionless import validate`

**Arguments**:

- `source` _dict|str_ - a data source
- `type` _str_ - source type - inquiry, package, resource, schema or table
- `**options` _dict_ - options for the underlaying function
  

**Returns**:

- `Report` - validation report

## validate\_inquiry

```python
@Report.from_validate
validate_inquiry(source, *, parallel=False, **options)
```

Validate inquiry

API      | Usage
-------- | --------
Public   | `from frictionless import validate_inquiry`

**Arguments**:

- `source` _dict|str_ - an inquiry descriptor
- `parallel?` _bool_ - enable multiprocessing
  

**Returns**:

- `Report` - validation report

## validate\_package

```python
@Report.from_validate
validate_package(source, noinfer=False, nolookup=False, parallel=False, **options)
```

Validate package

API      | Usage
-------- | --------
Public   | `from frictionless import validate_package`

**Arguments**:

- `source` _dict|str_ - a package descriptor
- `basepath?` _str_ - package basepath
- `trusted?` _bool_ - don't raise an exception on unsafe paths
- `noinfer?` _bool_ - don't call `package.infer`
- `nolookup?` _bool_ - don't read lookup tables skipping integrity checks
- `parallel?` _bool_ - enable multiprocessing
- `**options` _dict_ - Package constructor options
  

**Returns**:

- `Report` - validation report

## validate\_resource

```python
@Report.from_validate
validate_resource(source, *, checks=None, checksum=None, pick_errors=None, skip_errors=None, limit_errors=config.DEFAULT_LIMIT_ERRORS, limit_memory=config.DEFAULT_LIMIT_MEMORY, noinfer=False, **options, ,)
```

Validate table

API      | Usage
-------- | --------
Public   | `from frictionless import validate_table`

**Arguments**:

- `source` _any_ - the source of the resource
- `checks?` _list_ - a list of checks
- `checksum?` _dict_ - a checksum dictionary
  pick_errors? ((str|int)[]): pick errors
  skip_errors? ((str|int)[]): skip errors
- `limit_errors?` _int_ - limit errors
- `limit_memory?` _int_ - limit memory
- `noinfer?` _bool_ - validate resource as it is
- `**options?` _dict_ - Resource constructor options
  

**Returns**:

- `Report` - validation report

## validate\_schema

```python
@Report.from_validate
validate_schema(source, **options)
```

Validate schema

API      | Usage
-------- | --------
Public   | `from frictionless import validate_schema`

**Arguments**:

- `source` _dict|str_ - a schema descriptor
  

**Returns**:

- `Report` - validation report

