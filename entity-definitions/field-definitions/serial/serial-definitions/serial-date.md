# Serial date

## Description

Generates serial date values.

## Definitions

~~~
serial type(date)
    from(<Date>)                        # start from this date
    step( { <Integer> | <Decimal> } )	# incrementing by these days
~~~

## Notes

* The `step` parameter defines the number of days to increment.

## Examples

~~~
serial type(date) from(2018-01-01) step(3)
~~~
Result: 2018-01-01, 2018-01-04, 2018-01-07, 2018-01-10, ...