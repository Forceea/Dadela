# Serial number

## Description

Generates serial numbers.

## Definitions

~~~
serial type(number)
	from(<Number>)                      # the minimum number
    step(<Number>)                      # incrementing by this number
    [ scale(<PositiveInteger>) ]        # using this rounding
    [ format(<FormatString>) ]
    
<Number> := { <Integer> | <Decimal> }
~~~

## Examples

~~~
serial type(number) from(1) step(1.222) scale(2) format(000.000)
~~~