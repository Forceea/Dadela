# Random list

## Description

Generates random list values.

## Definitions

~~~
random type(list)
    value(<List>)
    [ except(<List>) ]
    [ iterations(<PositiveInteger> ]
    [ copies(<PositiveInteger>) ]
    [ separator(<String>) ]
~~~

## Notes

* The except parameter excludes items of the `value` argument list.
* The default value of the optional parameter `start` is the first list item of `value`.
* The default value of the optional parameters `iterations` and `copies` is 1.
* The default value of the optional parameter `separator` is <blank>.

The order of the optional parameters `iterations` and `copies` defines the process as follows:
* If `iterations` is before `copies`, Dadela will generate a random number `x` times
and then will copy the generated concatenated number `y` times.
* If `copies` is before `iterations`, Dadela will copy the generated number `x` times
and then will repeat the process `y` times.

## Examples

~~~
random type(list) value(!Months) separator(;)
random type(list) value(!Months) except(Feb, June) copies(3)
random type(list) value(!Months) except(Feb, June) copies(3) start(May)
random type(list) value(!Months) except(!SomeMonths) iterations(4) 

random type(list) value(!MyList1, item1, "item (2)", !MyList2) iterations(@myIterations + 1)
~~~