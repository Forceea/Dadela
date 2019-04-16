# Records

## Description

The `records` attribute is the default number of created entity records
when we execute the data generation process.

## Definitions

~~~
<records> := <PositiveInteger> | <Variable>
~~~

## Notes

* None.

## Examples

~~~
records: 100
records: @numberOfRecords          # get the value from a variable
records: 100.2	                   # ERROR
~~~