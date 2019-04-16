# Serial datetime

## Description

Generates serial datetime values.

## Definitions

~~~
serial type(datetime)
    from( { <Date> | <Datetime> } )             # start from this date or datetime
	step( { <Integer> | <Decimal> } )           # incrementing by these days
~~~

## Notes

* The `step` parameter defines the number of days to increment.

## Examples

~~~
serial type(datetime) from(2018-01-01) step(1.25) 
~~~
Result: 2018-01-01 00:00:00, 2018-01-02 06:00:00, 2018-01-03 12:00:00, 2018-01-04 18:00:00, ...