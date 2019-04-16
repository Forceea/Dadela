# Random numbers

## Description

Generates random numbers.

## Definitions

~~~
random type(number)
    from(<Number>)							# the minimum number
    to(<Number>)							# the maximum number
    [ scale(<PositiveInteger>) ]			# with this rounding
    [ iterations(<PositiveInteger>) ]		# repeat x times
    [ copies(<PositiveInteger>) ]			# copy x times
    
<Number> := { <Integer> | <Decimal> }
~~~

## Notes

* The default value of the optional parameters `iterations` and `copies` is 1.

The order of the optional parameters `iterations` and `copies` defines the process as follows:
* If `iterations` is before `copies`, Dadela will generate a random number `x` times
and then will copy the generated concatenated number `y` times.
* If `copies` is before `iterations`, Dadela will copy the generated number `x` times
and then will repeat the process `y` times.

## Examples

~~~
random type(number) from(1) to(100) scale(1) iterations(2) copies(2)
~~~
* first iteration: 52.2
* second iteration: 11.3
* Result: "52.211.3"
* Final Result: "52.211.352.211.3"

Please note that the above final result `52.211.352.211.3` is not an actual number,
but it could be considered a string.